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
- **vt.joinhandshake.com** — VT Handshake portal (login required; cannot be scraped with `site:` queries). Browse directly at https://vt.joinhandshake.com/stu/collections — filter by **Technology**, **Engineering**, and **Manufacturing** collections.

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
site:linkedin.com/jobs "additive manufacturing intern" United States
site:linkedin.com/jobs "directed energy deposition" intern United States
site:linkedin.com/jobs "aerospace" "manufacturing" intern United States
site:indeed.com "additive manufacturing" internship United States
site:indeed.com "additive manufacturing intern" United States
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

### Priority 2b — Structures & FEA (aerospace structures / simulation)

```
site:linkedin.com/jobs "structures engineer" intern aerospace United States
site:linkedin.com/jobs "structural analysis" intern United States
site:linkedin.com/jobs "FEA engineer" intern United States
site:indeed.com "FEA" intern "finite element" United States
site:indeed.com "structures engineering intern" United States
site:linkedin.com/jobs "structures engineering intern" United States
```

### Priority 3 — Wider net (still on-profile)

```
site:linkedin.com/jobs "advanced manufacturing" intern United States
site:linkedin.com/jobs "manufacturing engineer intern" United States
site:linkedin.com/jobs "manufacturing summer intern" aerospace United States
site:linkedin.com/jobs "mechanical engineering intern" manufacturing United States
site:linkedin.com/jobs "engineering intern" aerospace manufacturing United States
site:indeed.com "mechanical engineering intern" manufacturing United States
site:indeed.com "manufacturing engineer intern" United States
site:indeed.com "mechanical engineering" co-op manufacturing United States
site:linkedin.com/jobs "materials science" intern manufacturing United States
site:linkedin.com/jobs "manufacturing engineering" intern United States
```

### Priority 3b — Welding / CAD / Simulation (manufacturing adjacent)

```
site:linkedin.com/jobs "welding engineer" intern United States
site:linkedin.com/jobs "simulation engineer" intern manufacturing United States
site:linkedin.com/jobs "CAD engineer" intern manufacturing United States
site:linkedin.com/jobs "process engineer" intern manufacturing aerospace United States
site:indeed.com "welding" intern "additive" OR "manufacturing" United States
site:indeed.com "simulation" intern "finite element" OR "FEA" United States
site:indeed.com "CAD" internship manufacturing United States
site:linkedin.com/jobs "design engineer" intern manufacturing aerospace United States
```

### Priority 3c — Targeted company career pages

Search directly on company career portals for the highest-priority employers. Use these in addition to LinkedIn/Indeed when running a targeted sweep.

**Welding / DED / Wire AM**
```
site:lincolnelectric.com intern OR internship engineering
site:esab.com intern OR internship
"Lincoln Electric" "intern" "engineering" site:linkedin.com/jobs United States
"Sciaky" intern site:linkedin.com/jobs United States
"ESAB" intern "manufacturing" OR "welding" site:linkedin.com/jobs United States
```

**Metal Additive Manufacturing**
```
"EOS" intern "additive manufacturing" site:linkedin.com/jobs United States
"Velo3D" intern site:linkedin.com/jobs United States
"Trumpf" intern "manufacturing" site:linkedin.com/jobs United States
"Desktop Metal" intern site:linkedin.com/jobs United States
"Relativity Space" intern site:linkedin.com/jobs United States
```

**CAD / Simulation software companies**
```
site:ansys.com/careers intern OR internship
site:3ds.com/careers intern OR internship
"Dassault Systèmes" OR "SolidWorks" intern internship site:linkedin.com/jobs United States
"Siemens" intern "simulation" OR "manufacturing" site:linkedin.com/jobs United States
"Autodesk" intern "manufacturing" OR "CAD" site:linkedin.com/jobs United States
"Hexagon" intern manufacturing simulation site:linkedin.com/jobs United States
```

**Aerospace manufacturing (non-defense or explicitly F-1 friendly)**
```
"GE Aerospace" intern "manufacturing" OR "simulation" site:linkedin.com/jobs United States
"Safran" intern "manufacturing" United States site:linkedin.com/jobs
"Spirit AeroSystems" intern site:linkedin.com/jobs United States
"Pratt Whitney" intern "manufacturing" site:linkedin.com/jobs United States
```

### Priority 4 — Virginia Tech / Virginia regional (optional)

```
site:linkedin.com/jobs intern "Virginia Tech" OR Blacksburg engineering
site:indeed.com internship engineering Virginia
```

### VT Handshake (browse directly — login required)

**URL:** https://vt.joinhandshake.com/stu/collections

Handshake blocks web indexing — do not use `site:` queries. Browse the following collections directly inside the portal:
- **Technology** collection
- **Engineering** collection
- **Manufacturing** collection

Inside each collection, search with these keywords:
```
additive manufacturing
metal additive
directed energy deposition
structures engineering
FEA / finite element
mechanical engineering intern
manufacturing engineer intern
welding engineer
simulation engineer
CAD engineer
```

Filter: **Job type = Internship/Co-op**, **Location = United States** (or specific states). Apply the eligibility exclusion rules below before shortlisting any posting.

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

## Eligibility exclusion (F-1 international student)

The candidate holds an **F-1 visa (CPT/OPT eligible)** — she is NOT a US citizen, US national, or permanent resident.

**INELIGIBLE — do not add to tracker. Discard silently.**
Any posting containing (exact or paraphrased):
- "US citizen only" / "US citizenship required"
- "US national" / "US nationals only"
- "US person" (ITAR/EAR definition)
- "permanent resident required" / "green card required"
- "must be authorized to work without visa sponsorship"
- "must be eligible for export-controlled work without sponsorship"
- "active security clearance required"
- ITAR-controlled position with explicit citizenship language

**REVIEW — add to tracker with `Eligibility = REVIEW`, leave Status blank until verified.**
- General ITAR/EAR language without explicit citizenship requirement → flag "verify with employer + VT ISO"
- Defense prime (Boeing, Lockheed, Northrop, Raytheon, etc.) without explicit citizenship language → flag "defense prime — check posting for citizenship clause"
- "Ability to obtain security clearance" → flag "may be open to F-1; verify with employer"
- "US work authorization required" without citizenship language → F-1 with CPT/OPT is valid; mark **OK**

**OK — eligible as F-1 with CPT/OPT authorization.**

---

## Adding results to the tracker

File: `internship_tracker.csv`

Columns: `Company, Job Role, Term, Deadline, Location, Key Skills Required, Eligibility, Fit, Score, CV File, URL, Status`

Rules:
1. **Sort all rows by Deadline (earliest first).** Rows with unknown deadlines go at the bottom.
2. Set **Eligibility** using the exclusion rules above (INELIGIBLE / REVIEW / OK).
3. Leave **Fit**, **Score**, **CV File**, and **Status** blank — these are filled when `/apply` is run.
4. **Status values:** *(blank)* = not yet applied · `Ineligible` · `Applied` · `Interview` · `Offer` · `Rejected`
5. If deadline is not listed in the posting, write `Unknown`.

---

## Adapting queries

If the user specifies a focus area (e.g. “wire DED”, “AFSD”, “FEA manufacturing”):

- Pull from the closest priority block and add **2–3 custom** `WebSearch` lines with that focus + **United States** (or FR/DE if requested).

Example:

- `/scrape friction stir additive` → custom queries with `"friction stir"` / `AFSD` / `solid-state additive` + intern/co-op + United States.
