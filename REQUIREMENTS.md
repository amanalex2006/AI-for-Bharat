# REQUIREMENTS DOCUMENT

## AI Team Formation Assistant (Hackathon MVP)

------------------------------------------------------------------------

## 1. Purpose

Define the functional and non-functional requirements for a
hackathon-scale system that helps a user:

-   describe a project idea\
-   receive an AI-generated execution roadmap\
-   view recommended people for required roles\
-   select a team while remaining fully in control

The system focuses on removing the hassle of finding the right
collaborators, not automating hiring or execution.

------------------------------------------------------------------------

## 2. Scope

### Included in MVP

-   Free-form project idea input\
-   AI-generated:
    -   project summary\
    -   feature list\
    -   required roles\
    -   suggested tech stack\
    -   rough timeline\
-   Recommended candidate list per role\
-   Human team selection interface\
-   Single-page visual dashboard

### Explicitly Excluded

-   Real hiring or contracts\
-   Payment or escrow systems\
-   Messaging or collaboration tools\
-   Live scraping of freelance platforms\
-   Full project management features

------------------------------------------------------------------------

## 3. Functional Requirements

### 3.1 Idea Submission

The system shall:

-   Allow a user to enter a textual project description\
-   Validate that input is non-empty\
-   Send the idea to a backend API for processing

------------------------------------------------------------------------

### 3.2 AI Roadmap Generation

The backend shall:

-   Send the idea to an external language-model inference service\
-   Generate structured output containing:
    -   project summary\
    -   core features\
    -   required roles\
    -   suggested technology stack\
    -   estimated development phases
-   Return the result as structured JSON

------------------------------------------------------------------------

### 3.3 Candidate Recommendation

For each required role, the system shall:

-   Display 3--5 suggested candidates\
-   Show:
    -   skills or specialization\
    -   experience indicator\
    -   estimated cost range\
    -   match score

Candidate data may be predefined mock data or sourced from publicly
available developer platforms.

------------------------------------------------------------------------

### 3.4 Team Selection

The user shall be able to:

-   Add or remove suggested candidates\
-   View a final selected team list\
-   Retain full decision-making control

The AI shall only recommend, not auto-assign.

------------------------------------------------------------------------

### 3.5 Dashboard Visualization

The frontend shall present on a single screen:

-   Project overview\
-   Feature roadmap\
-   Required roles\
-   Recommended candidates\
-   Selected team

------------------------------------------------------------------------

## 4. Non-Functional Requirements

### Performance

-   Roadmap generation time ≤ 60 seconds\
-   UI interaction latency ≤ 2 seconds

### Reliability

-   Graceful handling of AI or network failures\
-   Clear user-visible error messages\
-   No full application crash from malformed responses

### Usability

-   ≤ 3 steps from idea to team view\
-   Clear visual hierarchy\
-   Minimal learning curve

### Security (Hackathon Level)

-   No storage of sensitive personal data\
-   API keys stored in environment variables\
-   Basic request validation

### Deployability

-   Containerized backend deployment\
-   Cloud hosting compatibility\
-   Environment-based configuration

------------------------------------------------------------------------

## 5. Acceptance Criteria

A user can:

1.  Enter a project idea\
2.  Receive an AI-generated roadmap\
3.  View recommended people for each role\
4.  Select a team

All within one minute.
