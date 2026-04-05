# Job Scraper

**name:** job-scraper
**description:** Searches US, French, and German job sources (LinkedIn, Indeed, Glassdoor, etc.) for roles and internships matching the configured profile. Deduplicates across runs. Triggers on: job scrape, find jobs, search jobs, new jobs, job search, scrape jobs, internship search, summer internship, co-op, /scrape
**allowed-tools:** Read, Write, Edit, Glob, Grep, WebFetch, WebSearch, Agent, AskUserQuestion

---

## How It Works

This skill runs **WebSearch/WebFetch** using **`search-queries.md`** in this directory (USA-first; France and Germany as secondary blocks). **Do not** use Danish job sites or repo `.agents/skills/` Denmark tools unless the user explicitly asks for Denmark.

**Profile & eligibility:** Read **`.cursor/skills/job-internship-search/PROFILE-SEARCH.md`** for markets, **F-1 / CPT / OPT** rules, deal-breakers, and technical fit themes (metal AM, DED, AFSD, aerospace manufacturing). Before scoring fit, read **`.claude/skills/job-application-assistant/01-candidate-profile.md`** (and `02-behavioral-profile.md` if present). If candidate files still contain `[PLACEHOLDER]` values, rely on PROFILE-SEARCH for fit and tell the user to run `/setup` or fill profiles when possible.

It deduplicates against **`job_scraper/seen_jobs.json`** and **`job_search_tracker.csv`**, then presents new matches with a quick fit assessment and **visa/eligibility** flags where relevant.

## Invocation

The user triggers this skill by saying things like:
- "Find new jobs"
- "Scrape for jobs"
- "Any new positions?"
- "/scrape"

Optional arguments:
- A focus area, e.g. "/scrape additive manufacturing" or "/scrape DED"
- **"broad"** to run all US categories in `search-queries.md` (and secondary FR/DE blocks only if the user also wants EU or results are thin)
- **"France"** or **"Germany"** to prioritize that region’s query block

---

## Execution Steps

### Step 0: Load State

1. Read `job_scraper/seen_jobs.json` (create if missing — start with `{"seen": {}}`)
2. Read `job_search_tracker.csv` to extract already-applied companies+roles
3. Read `search-queries.md` (this directory) for query templates and location rules
4. Read `.cursor/skills/job-internship-search/PROFILE-SEARCH.md` for eligibility, geography, and deal-breakers

### Step 1: Search

Run **WebSearch** using queries from **`search-queries.md`**.

- **Default:** Run **US Priority 1–3** (and **P4** if the user wants regional Virginia / Blacksburg focus).
- **"broad":** Run all US priority blocks in `search-queries.md`. Add **France** and **Germany** blocks only if the user asked for EU expansion, named FR/DE, or said US results were insufficient.
- **Internships:** Prefer internship/co-op query lines in `search-queries.md` and language from PROFILE-SEARCH (intern, co-op, summer intern, PhD intern, etc.).

If the user specified a focus area, prioritize matching queries and add 2–3 custom `WebSearch` lines for that focus.

For each search:

- Use `WebSearch` with the **site filters and keywords** in `search-queries.md` (LinkedIn, Indeed, Glassdoor, etc. — **not** Danish boards unless the user requested Denmark).
- Respect **Location Filter** and **Active region** in `search-queries.md` and **PROFILE-SEARCH**.
- Prefer postings from the **last 14 days**.

### Step 2: Fetch & Parse

For each promising result from Step 1:

- Use `WebFetch` to retrieve the job posting page when needed.
- Extract: **job title**, **company**, **location**, **posting date** (or "recent"), **URL**, **key requirements** (brief), **application deadline** (if listed), and **any citizenship / visa / clearance** language.
- Skip if the URL or company+title combo already exists in `seen_jobs.json`.
- Skip if the company+role already appears in `job_search_tracker.csv`.
- Per **PROFILE-SEARCH**, **drop or mark ineligible** postings that are **US citizen only**, **green card only**, or clearly exclude **F-1 / CPT / OPT** without an international-student path. **Flag** ITAR/clearance/defense/lab roles for manual review unless the posting explicitly welcomes F-1/CPT/OPT.

### Step 3: Quick Fit Assessment

For each new job, do a rapid fit check (NOT the full evaluation from `04-job-evaluation.md`):

- **High match:** Role directly involves core themes from PROFILE-SEARCH (metal AM, DED, AFSD, aerospace/advanced manufacturing, process R&D).
- **Medium match:** Adjacent (general ME, materials, manufacturing, FEA) with plausible bridge to profile.
- **Low match:** Requires a different primary skill set with little overlap.

### Step 4: Deduplicate & Store

1. Add ALL fetched jobs (new and skipped) to `seen_jobs.json` with structure:

```json
{
  "seen": {
    "<url_or_company_title_key>": {
      "title": "...",
      "company": "...",
      "url": "...",
      "first_seen": "YYYY-MM-DD",
      "fit": "high/medium/low",
      "status": "new/skipped/evaluated",
      "eligibility": "ok|flag|ineligible"
    }
  }
}
```

2. Only present jobs NOT already in the seen list or tracker (except ineligible may be summarized separately if useful).

### Step 5: Present Results

Present new jobs in a table sorted by fit (high first). Include an **Eligibility** column when visa/citizenship language was found: **OK**, **Review** (ITAR/clearance/ambiguous), or **Ineligible** (citizen/green-card-only).

```
## New Job Matches - YYYY-MM-DD

Found X new positions (Y high, Z medium, W low match).

| # | Fit | Eligibility | Title | Company | Location | Deadline | URL |
|---|-----|---------------|-------|---------|----------|----------|-----|
| 1 | High | OK | ... | ... | ... | ... | [Link](...) |

### High-Match Highlights
For each high-match job, add 2–3 bullet points:
- Why it matches your profile
- Key requirements to check
- Any red flags (including visa/export control if relevant)
```

After presenting, ask:

> "Want me to evaluate any of these in detail? Just give me the number(s)."

If the user picks a number, invoke the **job-application-assistant** skill workflow (fit evaluation first, then CV + cover letter if approved).

### Step 6: Update Tracker (Optional)

If the user decides to apply to any job, add a row to `job_search_tracker.csv`.

---

## Important Rules

1. **Never fabricate job postings.** Only present jobs found via actual WebSearch/WebFetch results.
2. **Respect deduplication.** Always check `seen_jobs.json` AND `job_search_tracker.csv` before presenting.
3. **Geography:** **USA primary**; **France / Germany** only when the user asks or `search-queries.md` secondary blocks apply. **Do not** use Danish sites or Denmark agent skills unless the user explicitly requests Denmark.
4. **F-1 / eligibility:** Follow **PROFILE-SEARCH** — filter citizen-only and green-card-only roles; flag defense/labs/clearance-heavy postings.
5. **Only open positions.** Skip postings with expired deadlines or those marked as closed.
6. **Be efficient with WebFetch.** Do not fetch every search result — use titles and snippets to pre-filter before fetching.
7. **Parallel searches.** Use the Agent tool or parallel WebSearch calls to speed up the search phase.
