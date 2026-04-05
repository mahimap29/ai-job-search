---
name: job-internship-search
description: >-
  Finds internships, trainee programmes, graduate schemes, co-ops, thesis collaborations,
  and student-friendly roles aligned with the user's profile. Uses PROFILE-SEARCH.md,
  CLAUDE.md, and job-application-assistant candidate files for keywords, location, and
  fit. Deduplicates via internship_search state files. Use when the user asks for
  internships, summer placements, praktik, studiejob, graduate programmes, co-op, research
  intern, early-career roles, or "jobs for students/new grads".
---

# Job & internship search (profile-driven)

## Before searching

1. Read [PROFILE-SEARCH.md](PROFILE-SEARCH.md) in this folder — primary source for **queries, constraints, and deal-breakers**.
2. If present and not placeholder-only, also read:
   - `CLAUDE.md` (repo root)
   - `.claude/skills/job-application-assistant/01-candidate-profile.md`
   - `.claude/skills/job-application-assistant/02-behavioral-profile.md`
3. Merge constraints: **location, authorization, start date, remote policy, deal-breakers** from PROFILE-SEARCH + candidate files. If something conflicts, prefer PROFILE-SEARCH for search radius and internship-specific rules.

## Regional job boards

Read **PROFILE-SEARCH.md** for the target market. If it specifies **USA only** (or equivalent), **do not** use Danish `.agents/skills/` job boards unless the user explicitly asks. If PROFILE-SEARCH or the user names Denmark/EU, then prefer `.agents/skills/` (jobindex, jobnet, jobbank, jobdanmark) and complement with WebSearch. Otherwise use **WebSearch** (and any sites listed in PROFILE-SEARCH) only.

## Search execution

1. **State:** Ensure `internship_search/` exists. Read `internship_search/seen_postings.json` (create with `{"seen": {}}` if missing). Read `job_search_tracker.csv` if it exists — skip company+title (or URL) combinations already applied or seen.
2. **Queries:** Run WebSearch using PROFILE-SEARCH priority templates; default to **P1 + P2** unless the user asks for a "broad" sweep (then add P3). If the user names a focus (e.g. "ML intern"), add 2–3 tailored queries.
3. **Recency:** Prefer postings from the **last 14 days** or deadlines not yet passed; flag "date unknown" when needed.
4. **Fetch:** WebFetch only for promising hits; do not fabricate listings.
5. **Fit (quick):** Classify **high / medium / low** vs the user's **skills, degree, and stated themes** from PROFILE-SEARCH + candidate profile — not the full `04-job-evaluation.md` workflow.
6. **Store:** Add fetched entries to `seen_postings.json`:

```json
{
  "seen": {
    "<stable_key_url_or_company_title>": {
      "title": "...",
      "company": "...",
      "url": "...",
      "first_seen": "YYYY-MM-DD",
      "fit": "high|medium|low",
      "type": "internship|trainee|graduate|studiejob|other"
    }
  }
}
```

7. **Present:** Table sorted by fit (high first): Fit | Title | Company | Location | Deadline | URL. Short bullets for **high** matches (why it fits, one requirement to verify, one flag if any).

After results, ask whether to **evaluate one in depth** — then follow **job-application-assistant** (evaluate fit, then CV/cover letter if approved).

## Rules

- Never invent postings or URLs.
- Respect **deal-breakers**, **geography** (USA vs secondary markets named in PROFILE-SEARCH), and **visa/eligibility** rules there — e.g. F-1/CPT/OPT: drop or flag **US citizen only** / **green card only** postings; treat defense/lab roles with extra scrutiny.
- If PROFILE-SEARCH is mostly placeholders, tell the user which sections to fill, then run a **narrow** search with whatever is already known.

## Optional tracker

If the user applies, add a row to `job_search_tracker.csv` (or a dedicated sheet they use) — match whatever column convention the repo already uses.
