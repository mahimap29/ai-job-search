# Job Evaluation Framework — Mahima Prajapati

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** Abaqus FEA (expert), MATLAB, SolidWorks, CATIA, ANSYS, thermo-mechanical simulation, metal additive manufacturing process simulation, aeroelastic analysis, structural dynamics, CAD/CAM
**Moderate match areas:** AutoCAD Electrical, PLC programming (CoDeSys/RSlogix), RobotStudio, industrial automation concepts
**Weak match areas:** Python/programming-heavy data science, software development, CFD solvers (e.g., OpenFOAM, Fluent), propulsion, avionics, electrical systems design

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** Metal additive manufacturing (simulation/FEA), aeroelasticity research, aerospace structures, thermo-mechanical analysis, FEA simulation (Abaqus), teaching/technical communication
**Moderate:** Mechanical design (SolidWorks/CATIA), aerospace maintenance (Air India internship), industrial automation (PLC/ABB Robot internship), project coordination
**Entry-level:** Manufacturing operations, avionics, propulsion, software engineering roles

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Ideal culture signals:** Research-oriented, autonomous, technically rigorous, values innovation, cross-functional collaboration, fast-paced project delivery, invests in intern/student development

**Red flags to research:** Roles dominated by sustaining engineering/maintenance only, heavy bureaucracy with no research component, cultures that don't value independent thinking. Check Glassdoor, LinkedIn, and network contacts.

### 4. Location & Logistics (Pass/Fail + Notes)
- **US-wide internship (Summer/Fall 2026):** PASS — relocation is acceptable
- **France or Germany internship:** PASS (if user requested EU) — verify visa/authorization requirements; flag "confirm with VT International office and employer re: F-1 work abroad"
- **Requires US citizenship / green card / active security clearance:** FAIL — immediate disqualifier; do not proceed with application
- **"US national only", "US person", "security clearance required":** FAIL — flag prominently before any work begins
- **CPT/OPT friendly, visa sponsorship offered:** PASS
- **Remote (US-based):** PASS — flag "verify F-1 remote work eligibility with VT International office"

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Build industry experience in metal additive manufacturing or aerospace structures/simulation during PhD
- Develop FEA/simulation expertise applicable to real manufacturing problems (bridge research to industry)
- Grow into a research engineer or senior simulation engineer role post-PhD

**Motivation filter — Tasks that energize:**
- Running and interpreting FEA/simulation studies on real components
- Solving complex engineering problems that have never been solved before
- Designing or improving AM processes using computational tools
- Teaching, explaining, or documenting technical findings to others
- Presenting research and receiving expert feedback

**Tasks that drain:**
- Purely administrative or coordination work with no technical component
- Highly repetitive testing/operations without intellectual challenge
- Environments with no autonomy or creative latitude

**Life situation alignment:**
- **Visa:** F-1 CPT/OPT — sponsorship-friendly employers are strongly preferred; citizenship/clearance-required roles are disqualified
- **Timing:** Summer 2026 and Fall 2026 internships; PhD in early stage (started Jan 2025)
- **Professional development:** Every internship should add to simulation, AM, or aerospace structures experience directly relevant to PhD research

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Visa/Eligibility Check
- [ ] Posting does NOT contain: "US citizen only", "US national", "green card required", "active clearance required", "US person"
- [ ] Employer hires F-1 visa holders (CPT/OPT) OR offers sponsorship

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted. Visa eligibility failure = immediate disqualifier regardless of score.)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"
- "Is this role open to candidates on F-1 CPT/OPT?" (if not clear from posting)

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
