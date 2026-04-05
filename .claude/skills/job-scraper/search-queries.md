# Search Queries for Job Scraper

**Markets:** **United States (primary).** **France** and **Germany** (secondary — use when the user asks for EU or names a country). **Do not** use Danish boards (`jobindex.dk`, Jobnet, etc.) unless the user explicitly requests Denmark.

Eligibility and fit themes for the default profile live in **`.cursor/skills/job-internship-search/PROFILE-SEARCH.md`** (F-1, CPT/OPT, metal AM / DED / AFSD, deal-breakers).

---

## Active region

- **Default:** Run **US — Priority 1–3** queries below. Add **P4 (Virginia / Blacksburg)** if the user wants a local narrow search.
- **Broad US sweep:** Run all US priority blocks (P1–P4).
- **EU expansion:** Add **France** and/or **Germany** sections when the user asks for those countries or says US results are thin.

---

## Search sites (non-Danish)

**United States**

- **linkedin.com/jobs** — include `United States` or state in the query string.
- **indeed.com** — US postings; narrow with state or `United States`.
- **glassdoor.com** — job search (US).
- **joinhandshake.com** — if the user has Handshake access (university postings).

**France**

- **linkedin.com/jobs** — filter with `France` or French keywords (`stage`, `alternance`).
- **indeed.fr** — French postings.

**Germany**

- **linkedin.com/jobs** — filter with `Germany` or `Praktikum`.
- **indeed.de** — German postings.

**Company careers**

- Use `site:careers.COMPANY.com` or Google `careers` + company name + internship when targeting known employers (see PROFILE-SEARCH seeds).

---

## United States — query priorities

Substitute or narrow with state/region (e.g. Virginia) when the user asks. Keep **United States** in the string when possible to reduce off-market hits.

### Priority 1 — Best fit (AM / DED / aerospace manufacturing)

```
site:linkedin.com/jobs "additive manufacturing" intern United States
site:linkedin.com/jobs "directed energy deposition" intern United States
site:linkedin.com/jobs "aerospace" "manufacturing" intern United States
site:indeed.com "additive manufacturing" internship United States
site:indeed.com "directed energy deposition" internship United States
site:glassdoor.com "metal additive" intern United States
```

### Priority 2 — Research / labs / national programs (verify F-1 + citizenship language)

```
site:linkedin.com/jobs NASA internship engineering United States
site:indeed.com "research internship" materials manufacturing United States
site:linkedin.com/jobs "national laboratory" intern engineering United States
```

Many lab/defense postings require **US citizenship** or **US person** — check eligibility before recommending (see PROFILE-SEARCH).

### Priority 3 — Wider net (still on-profile)

```
site:linkedin.com/jobs "advanced manufacturing" intern United States
site:indeed.com "mechanical engineering" co-op manufacturing United States
site:linkedin.com/jobs "materials science" intern manufacturing United States
site:linkedin.com/jobs "manufacturing engineering" intern United States
```

### Priority 4 — Virginia Tech / Virginia regional (optional)

```
site:linkedin.com/jobs intern "Virginia Tech" OR Blacksburg engineering
site:indeed.com internship engineering Virginia
```

### Handshake / university (if applicable)

```
site:joinhandshake.com "additive manufacturing" internship
site:joinhandshake.com "aerospace" internship
```

(Do not invent Handshake URLs; search via WebSearch with `site:joinhandshake.com` only.)

---

## France — secondary queries

Use when the user requests **France** or **EU** expansion.

```
site:linkedin.com/jobs stage OR alternance "fabrication additive" France
site:linkedin.com/jobs intern OR internship "additive manufacturing" France
site:indeed.fr stage aéronautique fabrication
site:linkedin.com/jobs stage ingénieur matériaux France
```

---

## Germany — secondary queries

Use when the user requests **Germany** or **EU** expansion.

```
site:linkedin.com/jobs praktikum Werkstoffe additive Germany
site:linkedin.com/jobs internship "additive manufacturing" Germany
site:indeed.de Praktikum additive Fertigung
site:linkedin.com/jobs Praktikum Maschinenbau Fertigung Germany
```

---

## Location filter

When evaluating results:

- **Home base:** Blacksburg, VA (Virginia Tech). **US-wide** internships and relocation-friendly summer roles are in scope unless the user narrows geography.
- **Remote:** US-remote OK if employment is US-based and eligibility matches PROFILE-SEARCH (F-1 rules — flag “verify with international office” when unclear).
- **France / Germany:** Only include when the user asked for those markets; **F-1 students working abroad** requires separate visa/status checks — flag “verify with ISO / consulate / employer.”

---

## Date filter

Only include jobs posted within the **last 14 days**, or with an application deadline that has not yet passed. If posting date is unknown, include but flag **date unknown**.

---

## Adapting queries

If the user specifies a focus area (e.g. “wire DED”, “AFSD”, “FEA manufacturing”):

- Pull from the closest priority block and add **2–3 custom** `WebSearch` lines with that focus + **United States** (or FR/DE if requested).

Example:

- `/scrape friction stir additive` → custom queries with `"friction stir"` / `AFSD` / `solid-state additive` + intern/co-op + United States.
