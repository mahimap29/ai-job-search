# Job Application Assistant for Mahima Prajapati

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Mahima Prajapati, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Mahima Prajapati
- **Location:** Blacksburg, Virginia, USA (open to US-wide relocation for internships; secondarily open to France and Germany)
- **Email:** mahimap@vt.edu
- **LinkedIn:** linkedin.com/in/mahimaprajapati
- **Languages:** English (Professional Working), Hindi (Professional Working), Gujarati (Full Professional), Marathi (Limited Working), Spanish (Elementary)
- **Status:** PhD student, Virginia Tech — F-1 visa holder (CPT/OPT eligible); seeking Summer 2026 and Fall 2026 internships
- **LinkedIn headline:** "Aerospace Engineering Grad @ Virginia Tech | Metal Additive Manufacturing | Structures and Vibrations | Aeroelasticity"

### Education
- **PhD in Aerospace & Ocean Engineering** (Jan 2025 - present) - Virginia Tech, Kevin T. Crofton Dept. of Aerospace and Ocean Engineering
  - Focus: Metal additive manufacturing (AM); Abaqus-based simulations to predict deformations and distortions during the AM process
- **MS in Aerospace Engineering** (Aug 2021 - Dec 2024) - Virginia Tech
  - Thesis: "Flutter speed and frequency of aircraft wings with distributed electric propulsors, exploring ways to mitigate aeroelastic instabilities"
  - Topics: Aeroelasticity, fluid-structure interaction, distributed electric propulsion, structural dynamics
- **BE in Mechanical Engineering** (2016 - 2020) - M.H. Saboo Siddik College of Engineering, Mumbai, India

### Professional Experience
- **Graduate Research & Teaching Assistant** (Dec 2021 - Present) - **Virginia Tech** (Blacksburg, VA)
  - Conducting PhD research in metal additive manufacturing using Abaqus FEA simulations
  - Delivered lectures, tutorials, and lab sessions; provided technical guidance to 50+ students
  - Vibrational studies research on Broad Art Museum Monumental Staircase System (with Dr. Mehdi Setareh, 2021)
- **Student Assistant** (May 2024 - Aug 2024) - **VT Continuing and Professional Education** (Blacksburg, VA)
  - Administrative and logistical support for project managers; financial process management
- **Mechanical Engineering Intern** (Jun 2019 - Jul 2019) - **Automation & Control Systems / PLC Automation Training** (Pune, India)
  - Error diagnosis of critical circuits using CoDeSys and RSlogix 8.10.00
  - Improved efficiency and accuracy by 20% of a 6-axis ABB Robot; reduced downtime by 15% using RobotStudio 6.00
  - Redesigned complex electrical projects using AutoCAD Electrical, saving 70% of working cost
- **Engineering Intern** (Dec 2018 - Jan 2019) - **Air India Limited** (Mumbai, India)
  - Routine maintenance of aircraft engines (PW4056, CFM56, GE90/GE Nx) and APU at Mumbai International Airport
  - Improved engine efficiency by 20% of PW4056 engine in maintenance project

### Technical Skills
- **Primary:** Abaqus (expert — FEA/simulation, thermo-mechanical coupling, UMAT/VUMAT), MATLAB, SolidWorks, ANSYS, CATIA
- **Secondary:** LaTeX, AutoCAD Electrical, CoDeSys, RSlogix, RobotStudio, MATLAB Simulink
- **Domain:** Metal Additive Manufacturing, Aeroelasticity, Fluid-Structure Interaction, Structures & Vibrations, Thermo-Mechanical Analysis, Design Optimization, CAD/CAM
- **Software:** Abaqus, MATLAB, SolidWorks, ANSYS, CATIA, AutoCAD Electrical, RobotStudio, CoDeSys, RSlogix, LaTeX

### Certifications
- **MATLAB Onramp** - MathWorks
- **MATLAB Fundamentals** - MathWorks
- **MATLAB Simulink Onramp** - MathWorks
- **CIRTL at Virginia Tech Associate Badge** - CIRTL Network (teaching in higher education)
- **Getting Started with Technology: Think Like an Engineer** - online certification

### Publications
- Prajapati, M. et al. (2026). "Flutter speed and frequency of aircraft wings with distributed electric propulsors." AIAA SciTech Forum 2026. (Presented January 2026)
- Prajapati, M. et al. (2027). [Extension of SciTech 2026 work — title TBD]. AIAA SciTech Forum 2027. (In preparation)

### Awards
- **Tolson & Nerney Fellowship** - Virginia Tech
- **Business Card Making Competition** - [event/year TBD]

### Behavioral Profile
- **Independent researcher** - thrives in deep, focused, self-directed research environments
- **Fast-paced project worker** - energized by high-tempo project work with clear deliverables
- **Collaborative team player** - uses teamwork to accelerate projects and build team cohesion
- **Creative problem solver** - wired to think differently and approach engineering challenges from novel angles
- **Strengths:** FEA simulation depth, bridging computational and real-world manufacturing, teaching/mentoring, persistence
- **Growth areas:** Learning to delegate in team settings; growing communication of highly technical work to non-specialist audiences
- **Thrives in:** Research labs, engineering teams with autonomy, environments that value both depth and execution speed

### What Excites You
- Bridging the gap between computational modeling (FEA) and real-world manufacturing challenges
- Advancing aerospace structures, aeroelastic design, and metal additive manufacturing technology
- Mentoring and developing the next generation of engineers

### Target Sectors
- **Aerospace & Defense:** Boeing, Lockheed Martin, Northrop Grumman, GE Aerospace, Pratt & Whitney, Raytheon, Collins Aerospace, Spirit AeroSystems, Safran, Airbus
- **Metal Additive Manufacturing:** Sciaky, Trumpf, Relativity Space, Divergent Technologies, Desktop Metal, 3D Systems, Velo3D
- **National Labs (civilian only):** Oak Ridge National Laboratory (ORNL), NASA (civilian programs), Pacific Northwest National Lab, Argonne
- **France/Germany (secondary):** Safran, Airbus (Toulouse/Hamburg), Dassault Systèmes, MTU Aero Engines, Liebherr Aerospace

### Deal-breakers
- Job postings requiring US citizenship, green card, or security clearance ("US national only", "US citizen required", "active clearance required")
- Employers who do not hire F-1 visa holders on CPT/OPT
- Roles outside aerospace, manufacturing, mechanical engineering, or structures/simulation domain

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. **Critical check:** Verify the posting does NOT include citizenship/clearance-only language (see Deal-breakers above). If it does, flag immediately.
4. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
5. **Verify both documents** (see Verification Checklist below)
6. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page
