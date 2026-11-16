# NVCHWA Career Readiness Assistant

## Overview

The **NVCHWA Career Readiness Assistant** is an AI-supported career-development tool designed for current and former Nevada Community Health Worker Association (NVCHWA) students.

The assistant extends career support beyond CHW training by helping users assess their current career readiness, identify transferable skills, strengthen resumes, evaluate job postings, explore CHW-aligned roles, understand Nevada CHW certification pathways, prepare for interviews, and create practical next steps.

The system is designed to provide structured, consistent career guidance while preserving important boundaries around privacy, credential accuracy, employment claims, and human decision-making.

This repository presents the **portfolio architecture and user experience** of the assistant rather than the full production configuration or internal assessment files.

---

## What the Assistant Supports

The assistant provides several student-facing career-support pathways:

- Career Readiness Assessment
- Transferable-skills identification
- Resume development and review
- Job-posting comparison
- CHW and CHW-aligned career exploration
- Nevada CHW certification guidance
- Interview preparation
- Short-term career action planning

Students are not required to complete the full assessment before using the other career-support functions.

---

## Career Readiness Assessment

The assistant includes a structured **38-item Career Readiness Assessment**.

The assessment contains:

- 25 scored questions
- 13 profile, routing, and personalization questions
- Five scored career-readiness domains
- Conditional branching
- Single-select and multi-select routing
- Career-pathway classification
- Personalized recommendations

### Five Career-Readiness Domains

Each scored section contributes up to 20 points:

| Domain | Maximum |
|---|---:|
| Resume Readiness | 20 |
| Transferable Experience Readiness | 20 |
| Training & Credentials Readiness | 20 |
| Job Search Readiness | 20 |
| Interview Readiness | 20 |
| **Career Readiness Index** | **100** |

The final 0–100 result is called the **Career Readiness Index**.

It is used as a career-planning indicator rather than an academic grade, certification score, pass/fail result, or measure of intelligence or potential.

---

## Career Readiness Levels

The Career Readiness Index is interpreted across five planning bands:

| Index | Career Readiness Level |
|---|---|
| 0–39 | Getting Started |
| 40–59 | Building Career Readiness |
| 60–74 | Preparing for the Job Search |
| 75–89 | Application Ready |
| 90–100 | Strong Career Readiness |

Section-level results are also used to distinguish:

- High Priority areas
- Development Areas
- Functional Strengths
- Established Strengths

The system avoids manufacturing weaknesses when a user already demonstrates strong readiness.

---

## Career Pathways

The assistant classifies career guidance into four broad pathways:

### A. New or Limited Formal Experience

For students whose preparation may come primarily from:

- Training
- Volunteering
- Caregiving
- Community involvement
- Education
- Limited recent formal employment

Support emphasizes building an accurate professional narrative and identifying relevant skills without overstating experience.

### B. Transferable Career Experience

For students transitioning from fields such as:

- Customer service
- Hospitality
- Retail
- Food service
- Administration
- Other non-healthcare roles

Support focuses on translating existing skills into language relevant to CHW and CHW-aligned work.

### C. Adjacent Professional Experience

For students with experience in areas such as:

- Healthcare
- Public health
- Behavioral health
- Social services
- Education
- Human services
- Peer support

Support emphasizes legitimate overlap between existing professional responsibilities and CHW competencies.

### D. Established CHW / Advancement

For experienced CHWs or users pursuing:

- Specialization
- Leadership
- Advancement
- Higher-quality positions
- Strategic career progression

Support shifts away from basic remediation and toward professional positioning and advancement.

---

## Knowledge Architecture

The assistant is grounded in a structured seven-file knowledge architecture.

Each source has a separate role so that assessment logic, certification requirements, employment information, and career-support guidance do not become mixed together.

### Knowledge Components

**Production Master Instructions**  
Defines system behavior, source hierarchy, privacy rules, assessment-state management, anti-fabrication safeguards, escalation behavior, score-lock logic, and report generation.

**Assessment Runtime Question Bank**  
Controls the live assessment sequence, including exact question order, response structure, score mappings, branching, routing, and next-item logic.

**Career Readiness Assessment & Scoring Guide**  
Defines scoring formulas, readiness bands, pathway classification, priority logic, completion rules, and report requirements.

**CHW Career & Competency Reference**  
Provides career-relevant language for competencies practiced through NVCHWA foundational training while maintaining boundaries between classroom preparation and professional employment.

**Nevada CHW Certification Reference**  
Separates foundational CHW training from Nevada certification and provides current guidance for CHW I and CHW II pathways.

**Employment Knowledge File**  
Provides historical Nevada employer context, CHW-aligned job-title families, and search-expansion knowledge while requiring live verification for current openings.

**Career Support Standards & Resource Guide**  
Defines standards for resume support, transferable skills, job search, job-posting analysis, interviews, privacy, professional development, and career action planning.

A portfolio-safe overview of this architecture is included in:

`NVCHWA_Career_Readiness_Assistant_Knowledge_and_System_Architecture.pdf`

---

## System Architecture

```text
Training, Certification, Employment,
Assessment, and Career-Support Sources
                ↓
       Structured Knowledge Base
                ↓
      Production Instructions
                ↓
 Assessment Runtime + Scoring Logic
                ↓
     Career Readiness Assistant
                ↓
 ┌───────────────────────────────┐
 │ Career Readiness Assessment   │
 │ Transferable Skills Support   │
 │ Resume Guidance               │
 │ Job-Posting Comparison        │
 │ Job Exploration               │
 │ Certification Guidance        │
 │ Interview Preparation         │
 │ Career Action Planning        │
 └───────────────────────────────┘
                ↓
   Personalized Student Guidance
```

---

## Accuracy and Anti-Fabrication Safeguards

A central design principle is that the assistant may help users **communicate real experience more effectively**, but it must not create experience they do not have.

The system is designed to avoid inventing or exaggerating:

- Employment
- Job duties
- CHW experience
- Client or patient contact
- Certifications
- Accomplishments
- Metrics
- Skills
- Training completion
- Professional outcomes

The assistant distinguishes among:

- Direct CHW experience
- Adjacent or related professional experience
- Transferable experience
- Training experience

Classroom exercises, simulations, case studies, and assignments are not converted into professional employment.

---

## Training vs. Certification Safeguard

NVCHWA foundational training and Nevada CHW certification are treated as separate statuses.

The assistant does not assume that a user is a Nevada Certified CHW I or CHW II simply because they completed foundational training.

Certification titles are used only when the user explicitly reports holding the credential.

Questions requiring official eligibility decisions, record verification, or administrative review are referred to the appropriate certification authority or NVCHWA staff.

---

## Privacy and Data Minimization

The assistant is designed to use the minimum personal information necessary for career guidance.

Users are encouraged to remove unnecessary identifiers before submitting resumes or other career materials.

The assistant does not require sensitive information such as:

- Social Security numbers
- Banking information
- Dates of birth
- Medical records
- Mental-health information
- Patient or client information
- Protected health information
- Passwords
- Detailed trauma or family information

Employment gaps can be discussed using concise professional language without requiring disclosure of private circumstances.

---

## Resume Support

Resume guidance focuses on:

- Accuracy
- Relevance
- Clear organization
- Transferable skills
- Accomplishment-oriented language
- Appropriate training and certification wording
- Alignment with target roles

The assistant may clarify, reorganize, strengthen, and tailor real information.

It does not manufacture duties, metrics, accomplishments, or credentials to make a resume appear stronger.

---

## Transferable-Skills Support

The assistant can help users identify skills from experience including:

- Customer service
- Hospitality
- Retail
- Administrative work
- Healthcare
- Social services
- Volunteer work
- Caregiving
- Community involvement
- Education
- CHW training

Common transferable-skill areas include:

- Communication
- Active listening
- Organization
- Problem-solving
- Teamwork
- Service orientation
- Resource research
- Follow-up
- Scheduling
- Documentation
- Coordination
- Teaching and explaining information

The underlying experience remains accurately classified even when the skills overlap with CHW competencies.

---

## Job Search and Job-Posting Review

The assistant expands career exploration beyond the title **Community Health Worker**.

Depending on a user's background and goals, relevant role families may include:

- Community Health Worker
- Patient Navigator
- Health Navigator
- Resource Navigator
- Care Coordinator
- Patient Care Coordinator
- Community Outreach
- Community Engagement
- Peer Support
- Recovery Support
- Youth and Family Services
- Community Resource roles
- Program Coordination
- Population Health roles

Historical employer information is used only for career exploration.

Current job openings, salaries, employer hiring status, and time-sensitive requirements must be verified using current sources.

When reviewing a job posting, the assistant distinguishes among:

- Required qualifications
- Preferred qualifications
- Qualifications the student appears to meet
- Information the student has not provided
- Potential gaps
- Resume areas to emphasize
- Questions to verify with the employer

---

## Interview Support

Interview support can include:

- “Tell me about yourself”
- Transferable-skills explanations
- Behavioral interview questions
- CHW scenario questions
- Employment-gap responses
- Interviews with limited direct experience
- Full mock interviews
- Questions to ask an employer

During mock interviews, the assistant asks one question at a time.

Feedback emphasizes:

1. One thing the user did well
2. One specific area for improvement
3. Stronger organization or wording when useful

The assistant does not invent examples for the user to claim.

---

## Career Readiness Report

After valid assessment completion, the assistant generates a personalized Career Readiness Report that can include:

- Career Readiness Index
- Overall readiness level
- Assigned pathway
- Five section scores
- Strongest areas
- Priority or strategic development areas
- Roles to explore
- Resume next steps
- Training and credential next steps
- Job-search strategy
- Interview preparation
- 30-day career action plan

The report is designed to turn assessment results into practical next steps rather than simply producing a score.

---

## Validation and Regression Testing

The assistant was evaluated using controlled fictional student profiles representing all four career pathways.

### Core Assessment Benchmarks

| Profile | Pathway | Expected | Actual | Result |
|---|---|---:|---:|---|
| Denise | A – New/Limited Formal Experience | 38/100 | 38/100 | PASS |
| Jordan | B – Transferable Career Experience | 52/100 | 52/100 | PASS |
| Alicia | C – Adjacent Professional Experience | 77/100 | 77/100 | PASS |
| Marcus | D – Established CHW / Advancement | 97/100 | 97/100 | PASS |

Testing also evaluated:

- Question-sequence integrity
- Branching logic
- Scoring accuracy
- Pathway assignment
- Immediate final-report generation
- Post-assessment score preservation
- Transferable-skills classification
- Resume anti-embellishment behavior
- Job-posting comparison
- Certification escalation
- Interview privacy boundaries
- Stop/resume state preservation
- Live verification of current job information

All four benchmark pathways and all seven targeted post-assessment functional scenarios passed final validation.

---

## Design Improvements Identified Through Testing

Regression testing was used not only to verify outputs but also to identify and correct system defects.

Examples included:

- Assessment sequence drift
- Substitution of unofficial assessment questions
- Post-assessment report delays
- Score reconstruction errors
- Knowledge-package inconsistencies
- Ambiguous wording and formatting behavior

Corrections introduced:

- A dedicated runtime question bank
- Per-turn assessment-state verification
- Explicit next-item routing
- Final Score Lock
- Arithmetic verification before report generation
- Immediate report generation after valid completion
- Clear source hierarchy across knowledge files

---

## Repository Contents

This public repository contains portfolio documentation rather than the complete production configuration.

### Knowledge & System Architecture

`NVCHWA_Career_Readiness_Assistant_Knowledge_and_System_Architecture.pdf`

Provides a portfolio-safe overview of:

- Knowledge architecture
- Assessment design
- Runtime logic
- Scoring framework
- Career pathways
- Student-support modes
- Privacy safeguards
- Anti-fabrication rules
- Certification boundaries
- Validation approach

### Interface Screenshots

The repository also includes labeled screenshots showing the live user experience, including examples of:

- Assistant landing page
- Student entry pathways
- Transferable-skills guidance
- Interactive career-support options
- Assessment interactions
- Other student-facing workflows

The screenshots demonstrate how the underlying architecture is translated into an accessible conversational experience.

---

## Why the Production Files Are Not Included

The public repository intentionally does not include the complete:

- Production Master Instructions
- Assessment Runtime Question Bank
- Assessment & Scoring Guide
- Internal knowledge files
- Full production configuration

Those materials contain operational logic used by the live assistant.

Instead, this repository documents the architecture, design decisions, safeguards, validation approach, and user experience at a level appropriate for a public professional portfolio.

---

## Capabilities

The deployed assistant includes:

- Structured knowledge grounding
- Web search for current information
- Data-analysis capability
- Guided conversation starters
- Branching assessment logic
- Score calculation
- Career-pathway classification
- Personalized report generation
- Resume and job-posting analysis
- Career guidance
- Privacy protections
- Human escalation rules

---

## Project Purpose

This project demonstrates applied experience in:

- AI assistant design
- Knowledge-base architecture
- Instruction and prompt design
- Assessment development
- Scoring logic
- Branching conversational workflows
- State management
- Career-development systems
- Workforce development
- Community Health Worker education
- AI safety and anti-fabrication safeguards
- Privacy-conscious interaction design
- Regression testing
- Human-in-the-loop escalation
- User experience design

It was developed to explore how a structured AI assistant can extend practical career support while maintaining appropriate boundaries around factual accuracy, credentials, privacy, and human judgment.

---

## Status

**Current status: Validated prototype complete.**

The assistant has completed:

- Four-pathway core assessment regression testing
- Seven post-assessment functional validation scenarios
- Scoring and pathway verification
- Runtime sequence validation
- Privacy and anti-fabrication testing
- Certification-boundary testing
- Current-information verification testing
- Final report and score-lock validation

Future development could include:

- Limited student pilot testing
- User-experience feedback
- Usage analytics
- Staff implementation metrics
- Expanded reporting
- Additional career pathways
- Continued maintenance of certification and employment knowledge
- Evaluation of long-term student outcomes

---

## Important Note

The NVCHWA Career Readiness Assistant is a **career-support and decision-support tool**.

It does not replace:

- NVCHWA staff judgment
- The Nevada Certification Board
- Employer hiring decisions
- Official credential verification
- Professional career counseling when additional individualized support is required

Its purpose is to help users convert their actual training, experience, skills, and goals into clearer and more realistic pathways toward CHW and CHW-aligned employment.
