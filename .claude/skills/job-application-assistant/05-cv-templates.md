# CV Templates and Tailoring Guide — Mahima Prajapati

## Template: LaTeX moderncv (Banking Style)

All CVs use the moderncv LaTeX package with the "banking" style and "blue" color scheme.

**Output file:** `cv/main_<company>.tex`
**Compile with:** pdflatex (not xelatex)
**Master reference:** `cv/main_example.tex` (comprehensive CV with all competencies, experience, and achievements - use as source when building targeted CVs)

## Document Structure

```latex
\documentclass[11pt,a4paper,sans]{moderncv}
\moderncvstyle{banking}
\moderncvcolor{blue}

\usepackage[utf8]{inputenc}
\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    filecolor=magenta,
    urlcolor=blue,
    pdftitle={Mahima Prajapati - CV},
    pdfpagemode=FullScreen,
}
\usepackage[scale=0.77]{geometry}
\usepackage{import}

% Personal data
\name{Mahima}{Prajapati}
\address{Blacksburg, Virginia, USA}{}{}
\email{mahimap@vt.edu}
\extrainfo{\href{https://linkedin.com/in/mahimaprajapati}{LinkedIn}}

\begin{document}
\makecvtitle

% 1. Profile statement (1-3 sentences, tailored per role)
% 2. Core Competencies section
% 3. Professional Experience section
% 4. Education section
% 5. Publications
% 6. Honors and Awards
% 7. References

\end{document}
```

## Profile Statement Templates

### For Metal Additive Manufacturing / FEA / Simulation roles:
> PhD candidate in Aerospace Engineering at Virginia Tech specializing in metal additive manufacturing process simulation using Abaqus FEA. Expert in predicting thermo-mechanical deformations and distortions during AM processes, bridging the gap between computational modeling and real-world manufacturing outcomes. Published AIAA SciTech researcher with hands-on experience in Abaqus, MATLAB, SolidWorks, and CATIA; seeking to apply simulation expertise in an industry setting to accelerate next-generation manufacturing development.

### For Aerospace Structures / Aeroelasticity roles:
> PhD candidate in Aerospace Engineering at Virginia Tech with deep expertise in structural dynamics, aeroelasticity, and finite element analysis. MS thesis investigated flutter speed and frequency mitigation for aircraft wings with distributed electric propulsors; presented findings at AIAA SciTech 2026. Proficient in Abaqus, MATLAB, ANSYS, CATIA, and SolidWorks, with experience applying FEA to both aeroelastic and manufacturing simulation challenges. Passionate about advancing aerospace structural design through rigorous computational methods.

### For Mechanical Design / Manufacturing intern roles:
> Aerospace Engineering PhD candidate at Virginia Tech combining strong mechanical design skills (SolidWorks, CATIA, ANSYS) with advanced FEA simulation expertise (Abaqus). Background spans CAD/CAM, thermo-mechanical analysis, and manufacturing process simulation, complemented by internship experience in industrial automation (ABB robotics, PLC) and aircraft engine maintenance (Air India). Brings both computational depth and hands-on manufacturing perspective to mechanical engineering challenges.

### For Research Engineering / R&D roles:
> Aerospace Engineering PhD candidate at Virginia Tech with a strong publication record (AIAA SciTech 2026, 2027) and research expertise spanning metal additive manufacturing simulation and aeroelastic analysis. Combines independent research capability with collaborative team skills to deliver fast-paced technical results. Proficient in Abaqus, MATLAB, SolidWorks, CATIA, and ANSYS; experienced in teaching and communicating complex technical findings to diverse audiences. Seeks a research engineering internship to connect academic simulation work to industry-scale problems.

## Section-by-Section Tailoring

### Core Competencies / Skills Section (Best Practice)
Reorder and emphasize based on the role. Use bold category labels.

List **5-7 key competencies** in bullet format. Suggested competencies by role type:

**For AM / Manufacturing roles:**
- Finite Element Analysis (FEA): Abaqus expert — thermo-mechanical coupling, AM process simulation, deformation prediction
- CAD/CAM: SolidWorks, CATIA, AutoCAD Electrical — 3D design and manufacturing documentation
- Simulation Software: MATLAB, ANSYS — numerical analysis and structural validation
- Metal Additive Manufacturing: process understanding, computational modeling of DED/powder-bed processes
- Technical Communication: AIAA-published researcher; experienced instructor and technical mentor

**For Structures / Aeroelasticity roles:**
- Structural Dynamics & Aeroelasticity: flutter analysis, fluid-structure interaction, vibration studies
- FEA Simulation: Abaqus (expert), ANSYS — static/dynamic analysis of aerospace structures
- CAD Tools: SolidWorks, CATIA — design and structural modeling
- Computational Analysis: MATLAB — numerical methods, data processing, model development
- Research & Documentation: AIAA SciTech published author; LaTeX documentation

### Education
- Lead with PhD for research/engineering roles (credentials are a primary qualifier in aerospace)
- Include MS thesis title when relevant — it directly demonstrates aeroelastic expertise
- Include PhD research focus when applying to AM or structures roles

### Professional Experience
- Lead with Graduate Research & Teaching Assistant role — this is the most substantive
- Rewrite bullets to emphasize aspects most relevant to the target role
- Internship at Automation & Control Systems: emphasize automation, efficiency improvements (20%, 15%, 70% cost savings)
- Internship at Air India: emphasize aerospace domain exposure, engine system knowledge
- Use 4-5 bullets for most recent role, 2-3 for internships

### Publications
- Always include SciTech 2026 paper — it validates research credibility and aerospace domain expertise
- Mention SciTech 2027 forthcoming paper to show active research productivity

### Handling the PhD / Student Status
- Frame clearly: "PhD candidate" not "PhD student" in professional materials
- Explicitly state CPT/OPT eligibility in cover letter if not obvious from context (do not add to CV unless employer requests)
- Emphasize that internship experience directly complements and extends PhD research

## Page Budget - Hard 2-Page Limit

| Section | Max budget |
|---------|-----------|
| Profile statement | 3-4 lines |
| Core Competencies | 5-6 items, each 1-2 lines |
| Most recent role (GRA) | 4-5 bullets |
| Previous role (internship) | 2-3 bullets |
| Older roles | 1-2 bullets each |
| Education | 2-3 entries |
| Publications | 2 entries |
| Awards | 2-3 entries, single line each |
| References | "Available upon request." (single line) |

**If in doubt, cut rather than squeeze.**

## Recommended Section Order

**For Metal Additive Manufacturing / FEA / Simulation roles:**
1. Profile statement / elevator pitch
2. Core Competencies / Skills
3. Education (PhD credentials are a key qualifier)
4. Professional Experience (reverse chronological)
5. Publications
6. Honors and Awards
7. References

**For Aerospace Structures / Mechanical Design roles:**
1. Profile statement / elevator pitch
2. Core Competencies / Skills
3. Professional Experience (reverse chronological)
4. Education
5. Publications
6. Honors and Awards
7. References
