# Job Agent 🤖

> **An AI-powered job discovery and matching platform that actively searches for relevant opportunities based on a candidate's skills, experience, preferences, and career goals.**

Job Agent is a full-stack .NET application designed to help job seekers spend less time searching for jobs and more time applying to the right ones.

Instead of requiring users to repeatedly search multiple job boards, Job Agent uses an AI-powered agent to discover, analyse, and rank job opportunities based on each user's individual profile.

---

## 🚀 Overview

Traditional job searching requires candidates to:

- Search multiple job boards
- Repeat the same searches
- Read through hundreds of job descriptions
- Determine whether they meet the requirements
- Identify duplicate listings
- Track interesting opportunities manually

**Job Agent automates much of this process.**

A user creates a profile, uploads their CV, defines their job preferences, and allows the Job Agent to continuously search supported job sources.

The system then analyses available opportunities and determines which jobs are most relevant to the candidate.

```text
                         JOB AGENT
                            │
                            ▼
                   Candidate Profile
                            │
             ┌──────────────┼──────────────┐
             │              │              │
            CV          Preferences      Skills
             │              │              │
             └──────────────┼──────────────┘
                            ▼
                       AI JOB AGENT
                            │
                    Search Job Sources
                            │
                            ▼
                     Analyse Jobs
                            │
                            ▼
                    Match Candidates
                            │
                            ▼
                     Rank Results
                            │
                            ▼
                  Recommended Jobs
```

---

# ✨ Key Features

## 👤 Candidate Profiles

Users can create a professional job-seeker profile containing:

- Personal information
- Professional experience
- Education
- Skills
- Years of experience
- Preferred job titles
- Preferred industries/sectors
- Salary expectations
- Employment preferences
- Location preferences
- Remote/hybrid/on-site preferences

---

## 📄 CV Analysis

Users can upload their CV.

Job Agent extracts relevant information and uses AI to create a structured candidate profile.

```text
CV
 │
 ▼
Document Extraction
 │
 ▼
AI Analysis
 │
 ├── Skills
 ├── Experience
 ├── Job Titles
 ├── Education
 └── Technologies
 │
 ▼
Candidate Profile
```

This allows users to avoid manually entering every skill and job title.

---

## 🔎 AI-Powered Job Discovery

The Job Agent searches supported job sources for relevant opportunities.

The system is designed around a connector-based architecture so additional job sources can be added without changing the core application.

```text
                 JOB AGENT
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
   Career Pages   Job Sources   ATS Sources
        │            │            │
        └────────────┼────────────┘
                     ▼
              Job Normalisation
                     │
                     ▼
                 AI Analysis
```

---

## 🧠 Intelligent Job Matching

Each job is evaluated against the candidate's profile.

Job Agent considers factors such as:

- Skills
- Experience
- Job title
- Location
- Remote/hybrid/on-site preference
- Industry
- Salary
- Education
- Required technologies
- Preferred technologies

Example:

```text
.NET Developer
Pretoria | Hybrid
R40,000 - R50,000

Match Score: 92%

Skills             95%
Experience         100%
Location           100%
Work Arrangement   100%
Industry            85%
Salary              80%
```

The system can also explain **why** a job matches the candidate and identify potential gaps.

---

## 🤖 AI Job Agent

The core of Job Agent is an AI-powered agent capable of using application tools to perform job-search tasks.

Example tools may include:

```text
SearchJobs()
GetJobDetails()
AnalyseJob()
GetUserProfile()
MatchJob()
SaveJob()
FindSimilarJobs()
```

A typical agent workflow could look like:

```text
User:
"Find me .NET developer jobs in Pretoria."

        ↓

AI Agent
        ↓
Get Candidate Profile
        ↓
Search Supported Job Sources
        ↓
Analyse Job Listings
        ↓
Remove Duplicates
        ↓
Match Jobs Against Candidate
        ↓
Rank Results
        ↓
Return Best Opportunities
```

---

# 📊 Job Dashboard

Users can see recommended opportunities from a central dashboard.

Example:

```text
Good morning 👋

Your Job Agent found 27 new opportunities.

────────────────────────────────────

🔥 Strong Matches

94%   Senior .NET Developer
      Pretoria | Hybrid
      R45k - R55k

91%   C# Full Stack Developer
      Remote | South Africa
      R40k - R50k

88%   Software Developer
      Centurion | Hybrid
      R38k - R48k

────────────────────────────────────

Agent Activity

✓ 18 sources checked
✓ 143 listings discovered
✓ 67 duplicates removed
✓ 76 jobs analysed
✓ 27 matches found
```

---

# ❤️ Job Tracking

Users can manage opportunities through different stages:

```text
Saved
  ↓
Applied
  ↓
Interview
  ↓
Offer
```

Users can also mark jobs as:

- Not Interested
- Rejected
- Closed

This provides a lightweight application tracking system alongside the job discovery functionality.

---

# 🔔 Job Notifications

The Job Agent can notify users when relevant opportunities are discovered.

Possible notification channels include:

- In-app notifications
- Email notifications

Example:

> **Job Agent found 7 new opportunities**
>
> 3 opportunities have a match score above 90%.

---

# 🧩 Architecture

Job Agent is designed as a **modular monolith** rather than a collection of microservices.

The goal is to maintain a clean and maintainable architecture while keeping the system practical to develop and deploy.

```text
JobAgent
│
├── JobAgent.Web
│
├── JobAgent.Application
│
├── JobAgent.Domain
│
├── JobAgent.Infrastructure
│
├── JobAgent.AI
│
├── JobAgent.Agent
│
└── JobAgent.Tests
```

### Application Flow

```text
                 ┌─────────────────┐
                 │   Web / MVC UI  │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │   Application   │
                 │     Layer       │
                 └────────┬────────┘
                          │
              ┌───────────┼───────────┐
              ▼           ▼           ▼
           Domain       AI Agent   Matching
              │           │           │
              └───────────┼───────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ Infrastructure  │
                 └────────┬────────┘
                          │
             ┌────────────┴────────────┐
             ▼                         ▼
        SQL Server              External Sources
```

---

# 🛠️ Technology Stack

## Backend

- C#
- ASP.NET Core
- ASP.NET Core MVC
- REST APIs
- Dependency Injection
- Background Services

## Frontend

- Razor
- HTML5
- CSS3
- JavaScript
- jQuery
- Bootstrap
- DataTables

## Database

- Microsoft SQL Server

## AI

- Large Language Models (LLMs)
- AI Agent / Tool Calling
- Prompt Engineering
- CV Analysis
- Job Description Analysis
- Semantic Job Matching

The AI layer is designed to remain provider-independent where possible.

## Testing

- xUnit
- Moq

## DevOps

- Git
- Azure DevOps
- CI/CD

---

# 🗄️ Core Data Model

The initial data model will contain entities such as:

```text
Users
 │
 └── UserProfiles
       │
       ├── UserSkills
       ├── JobPreferences
       └── CVs


JobSources
 │
 └── Jobs
       │
       ├── JobSkills
       └── JobLocations


Users
 │
 ├── JobMatches
 ├── SavedJobs
 └── Applications


AgentRuns
 │
 ├── AgentTasks
 └── AgentErrors
```

Additional AI-related entities may include:

```text
AIAnalysis
AIModelRequests
AIUsage
```

---

# 🔄 Job Discovery Pipeline

The job discovery process follows a multi-stage pipeline.

```text
1. Discover
      ↓
2. Extract
      ↓
3. Normalise
      ↓
4. Deduplicate
      ↓
5. Analyse
      ↓
6. Match
      ↓
7. Rank
      ↓
8. Store
      ↓
9. Notify
```

This separation allows each stage to evolve independently.

---

# 🌐 Job Source Architecture

Job Agent uses a connector-based approach for external job sources.

```csharp
public interface IJobSource
{
    Task<IEnumerable<Job>> SearchAsync(
        JobSearchCriteria criteria);
}
```

Each supported source can implement the interface independently.

This allows new sources to be added without modifying the core matching engine.

> Job sources will only be integrated where appropriate access methods and applicable terms allow their use.

---

# 🔐 Security

Security will be treated as a core part of the application.

Planned features include:

- ASP.NET Core Identity
- Secure authentication
- Password hashing
- Role-based authorisation
- Protected CV/document access
- Input validation
- Secure API endpoints
- Secrets stored outside source control
- Audit logging for important actions

---

# 🧪 Testing Strategy

Testing will focus on the areas where incorrect results could significantly affect users.

### Unit Tests

Examples:

```text
✓ Job matching calculations
✓ Salary matching
✓ Location matching
✓ Skill matching
✓ Duplicate detection
✓ Job normalisation
✓ Agent tool behaviour
```

### Integration Tests

Examples:

```text
✓ Database operations
✓ Job-source connectors
✓ AI service integration
✓ Authentication
```

---

# 🗺️ Development Roadmap

## Phase 1 — Foundation

- [ ] Create solution structure
- [ ] Configure ASP.NET Core
- [ ] Configure SQL Server
- [ ] Implement authentication
- [ ] Create candidate profile
- [ ] Create job preferences
- [ ] Create initial database schema

## Phase 2 — Job Platform

- [ ] Job entity
- [ ] Job listing
- [ ] Job search
- [ ] Job details
- [ ] Save job
- [ ] Application tracking
- [ ] Job source abstraction

## Phase 3 — AI

- [ ] AI service abstraction
- [ ] CV text extraction
- [ ] CV analysis
- [ ] Job description analysis
- [ ] Skill extraction
- [ ] AI job matching
- [ ] Match explanations

## Phase 4 — Job Agent

- [ ] Agent architecture
- [ ] Agent tools
- [ ] Automated job discovery
- [ ] Job deduplication
- [ ] Background processing
- [ ] Agent activity history
- [ ] Scheduled searches

## Phase 5 — Notifications

- [ ] In-app notifications
- [ ] Email notifications
- [ ] Daily job summaries
- [ ] High-match alerts

## Phase 6 — Career Assistant

- [ ] CV recommendations
- [ ] Tailored CV suggestions
- [ ] Cover letter generation
- [ ] Skill-gap analysis
- [ ] Interview preparation

---

# 🎯 Project Goals

Job Agent is being developed to demonstrate practical experience with:

- Full-stack .NET development
- Clean application architecture
- SQL Server
- AI integration
- AI agents
- Tool calling
- Background processing
- External API integration
- Document processing
- Semantic matching
- Automated workflows
- Testing
- CI/CD

The project is also intended to explore how AI agents can solve practical problems rather than simply provide conversational interfaces.

---

# 📁 Repository Structure

```text
JobAgent/
│
├── src/
│   ├── JobAgent.Web/
│   ├── JobAgent.Application/
│   ├── JobAgent.Domain/
│   ├── JobAgent.Infrastructure/
│   ├── JobAgent.AI/
│   └── JobAgent.Agent/
│
├── tests/
│   ├── JobAgent.UnitTests/
│   └── JobAgent.IntegrationTests/
│
├── docs/
│
├── .gitignore
├── README.md
└── JobAgent.sln
```

---

# 🚧 Project Status

**Currently in development.**

Job Agent is being built incrementally, starting with the core job platform and evolving into an AI-powered job discovery agent.

---

# 📌 Future Vision

The long-term goal is for Job Agent to become more than a job search engine.

The system should act as a **personal career agent** that can:

```text
Understand the candidate
        ↓
Discover opportunities
        ↓
Evaluate opportunities
        ↓
Explain the match
        ↓
Track applications
        ↓
Identify skill gaps
        ↓
Help prepare applications
        ↓
Prepare for interviews
```

Instead of the candidate constantly searching for jobs, the goal is for the **job opportunities to come to the candidate**.

---

## 👨‍💻 Project

**Job Agent**

AI-powered job discovery and career matching platform.

Built with **C# / ASP.NET Core / SQL Server / AI**.
