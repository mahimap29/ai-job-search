# Internship & early-career search profile

**Markets:** **United States (preferred).** Secondary: **France, Germany** if the user asks or if US results are thin. **Do not** use Danish job sites or Denmark-focused repo skills unless the user explicitly requests Denmark.

The agent reads this file together with `CLAUDE.md` and `.claude/skills/job-application-assistant/01-candidate-profile.md` when those contain real data.

## Candidate summary (for fit scoring)

- **Name:** Mahima Prajapati  
- **Current role:** PhD student, **Virginia Tech** — Aerospace Engineering  
- **Education:**  
  - **BE**, Mechanical Engineering  
  - **MS**, Aerospace Engineering — focus **aeroelasticity**  
  - **PhD**, Aerospace Engineering — focus **metal additive manufacturing**, especially:  
    - **Laser wire directed energy deposition (DED)**  
    - **Additive friction stir deposition (AFSD)**  

Use this when judging **high / medium / low** match: metal AM, DED (wire/laser), solid-state additive (friction stir–family), aerospace structures, process development, experimental + characterization workflows typical of advanced manufacturing R&D.

## Identity & constraints

- **Home base:** Blacksburg, VA (Virginia Tech). Reasonable to consider **relocation** or **summer** internships elsewhere in the US.  
- **Work authorization:** **F-1 international student.** Internships must be viable under **CPT** and/or **OPT** (as applicable); the employer must **not** restrict roles to **US citizens only** or **US permanent residents (green card) only**.  
- **Eligibility (critical for the agent):**  
  - **Drop or clearly flag** postings that state: *US citizen only*, *US person only* (when meaning citizenship), *must be eligible for export-controlled work without sponsorship*, *permanent resident only*, *no visa sponsorship*, *ITAR/EAR — US citizen* without an international-student path, or equivalent.  
  - **Flag for manual review** (do not present as “safe”): defense primes, cleared facilities, national labs, and space/defense supply chain — many default to citizenship or “US person” requirements; still list if the text **explicitly** welcomes F-1/CPT/OPT or international students.  
- **Earliest start / duration:** [edit: e.g. May–Aug 2026, 10–12 weeks] — update when fixed.  
- **Remote / hybrid:** [edit: preference] — US-remote acceptable if posting is clearly US-employment and eligibility fits F-1 rules.

## What you are looking for

- **Primary:** Internships, co-ops, graduate research internships, and student R&D roles in **metal AM**, **DED**, **aerospace / advanced manufacturing**, **materials & process engineering**, or **mechanical design for AM** — with **no citizenship/green-card-only barrier**.  
- **Must-have themes:** Additive manufacturing, directed energy deposition, laser/wire AM, friction stir / AFSD, aerospace manufacturing, experimental process R&D, Manufacturing Engineering, Mechanical Design,  
- **Nice-to-have:** Alignment with thesis topics (DED, AFSD, Manufacturing, FEA), strong mentorship, publication-friendly environment, conference support.

## Search keywords (for WebSearch)

**Role types:** intern, internship, co-op, cooperative education, summer intern, graduate intern, PhD intern, research intern, student researcher, R&D intern

**Technical:** additive manufacturing, metal AM, directed energy deposition, DED, laser wire DED, wire additive manufacturing, WAAM (when relevant), additive friction stir deposition, AFSD, friction stir deposition, solid-state additive, aerospace manufacturing, advanced manufacturing, materials joining, process–structure–property

---

## USA — priority query templates

Default geography: **United States** or **USA** in the query. Prefer **LinkedIn**, **Indeed**, **Glassdoor**, **Handshake** (VT), and **company careers** pages.

### P1 — Best fit (AM / DED / aerospace manufacturing)

```
site:linkedin.com/jobs "additive manufacturing" intern United States
site:linkedin.com/jobs "directed energy deposition" intern United States
site:linkedin.com/jobs "aerospace" "manufacturing" intern United States
site:indeed.com "additive manufacturing" internship United States
site:indeed.com "directed energy deposition" internship United States
```

### P2 — University / national programs (verify F-1 + CPT/OPT on each posting)

```
site:linkedin.com/jobs NASA internship engineering United States
site:indeed.com "research internship" materials manufacturing United States
site:linkedin.com/jobs "national laboratory" intern engineering United States
```

(Agent: many lab/defense roles are citizenship-restricted — **check eligibility language** before recommending.)

### P3 — Wider net (still on-profile)

```
site:linkedin.com/jobs "advanced manufacturing" intern United States
site:indeed.com "mechanical engineering" co-op manufacturing United States
site:linkedin.com/jobs "materials science" intern manufacturing United States
```

### P4 — Virginia Tech & regional (optional narrow)

```
site:linkedin.com/jobs intern "Virginia Tech" OR Blacksburg engineering
site:indeed.com internship engineering Virginia
```

(Add **Handshake** or **Virginia Tech career services** only if the user or repo provides specific search instructions; do not invent URLs.)

---

## France & Germany — secondary (no Danish sites)

Use only when the user wants **EU expansion** or **France/Germany specifically**. **Do not** use `jobindex.dk`, Jobnet, or other Danish boards for this profile.

**France (examples):**

```
site:linkedin.com/jobs stage OR alternance "fabrication additive" France
site:linkedin.com/jobs intern OR internship additive manufacturing France
site:indeed.fr stage aéronautique fabrication
```

**Germany (examples):**

```
site:linkedin.com/jobs praktikum Werkstoffe additive Germany
site:linkedin.com/jobs internship additive manufacturing Germany
site:indeed.de Praktikum additive Fertigung
```

(Agent: confirm **work authorization** for each country; F-1 students taking work abroad is a separate immigration question — flag “verify visa/status with ISO.”)

---

## Companies & sectors to watch (seeds, not exhaustive)

Use for targeted `site:careers.COMPANY.com` searches. **Re-check every posting for citizenship/export-control language.**

- **AM / industrial:** EOS, Velo3D, DMG MORI, Lincoln Electric (wire processes), Optomec, Sciaky, GE Additive  
- **Aerospace & manufacturing:** GE Aerospace, Boeing, Lockheed Martin, Northrop Grumman, RTX — often restricted; only shortlist if posting allows **international students** or **CPT/OPT** explicitly  
- **Space / AM-forward:** Relativity Space, others — read eligibility carefully  
- **National labs / NASA:** high fit technically but **frequent citizenship requirements** — separate “citizenship likely required” bucket if listing at all  

## Deal-breakers

Hard filters (drop or mark **ineligible**):

- **US citizen only**, **green card only**, **permanent resident only**, or equivalent  
- **No visa sponsorship** when interpreted as excluding CPT/OPT-eligible F-1 employment (wording varies — prefer postings that explicitly allow **F-1**, **CPT**, **OPT**, or **international students**)  
- Locations **only** outside US / FR / DE when the user asked for US-only  
- No meaningful link to engineering, manufacturing, materials, aerospace, or AM (unless user broadens search)

Soft flags (still show, with warning):

- ITAR/EAR, “ability to obtain clearance,” government — verify with employer/ISO  
- Unpaid — user may still want awareness; flag clearly  

## Repo note

Denmark-focused tools live under `.agents/skills/`. **Do not use them** for this profile unless the user explicitly asks for Denmark.

**Full application workflow after shortlisting:** `.claude/skills/job-application-assistant/`.
