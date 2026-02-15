# DESIGN DOCUMENT

## AI Team Formation Assistant (Hackathon MVP)

------------------------------------------------------------------------

## 1. Objective

Design a hackathon-ready web system that converts a project idea into:

-   a structured execution roadmap\
-   recommended collaborators per role\
-   a human-selected starter team

AI assists planning and discovery, while humans retain control and
management.

Primary constraint: deliver a compelling live demo within 48 hours.

------------------------------------------------------------------------

## 2. High-Level Architecture

### Components

**Frontend Client** - Idea input interface\
- Roadmap visualization\
- Candidate recommendation view\
- Team selection panel

**Backend Service (Python FastAPI)** - REST API endpoints\
- Prompt orchestration\
- Structured response validation\
- Candidate data serving

**External AI Service** - Language-model inference for roadmap
generation

**Cloud Layer (Optional)** - Containerized deployment\
- Environment-based configuration

------------------------------------------------------------------------

## 3. Processing Flow

User Idea\
→ FastAPI `/generate` endpoint\
→ AI inference\
→ Structured roadmap JSON\
→ Candidate matching\
→ Frontend rendering\
→ Human team selection

------------------------------------------------------------------------

## 4. Backend Design

### Modules

**api/** -- routes\
**services/** -- AI + matching logic\
**schemas/** -- Pydantic models\
**data/** -- mock candidates\
**utils/** -- helpers and error handling

### Endpoint

POST `/generate`

Input: { "idea": "string" }

Output: - summary\
- features\
- roles\
- tech stack\
- phases\
- recommended candidates

------------------------------------------------------------------------

## 5. Frontend Design

Single-page dashboard:

1.  Project Overview\
2.  Feature Roadmap\
3.  Required Roles\
4.  Recommended Candidates\
5.  Selected Team

All visible without navigation.

------------------------------------------------------------------------

## 6. Data Strategy

-   Stateless MVP\
-   No required database\
-   Static JSON or lightweight public data

------------------------------------------------------------------------

## 7. Error Handling

-   Catch AI failures\
-   Return structured errors\
-   Allow retry

System must fail gracefully.

------------------------------------------------------------------------

## 8. Design Principles

-   Simplicity over completeness\
-   Human control over AI autonomy\
-   Strong demo clarity\
-   Fast deployment readiness

------------------------------------------------------------------------

## 9. Future Extensions

-   Persistent projects\
-   Real freelancer onboarding\
-   Messaging and payments\
-   Advanced AI matching

------------------------------------------------------------------------

## 10. Success Criteria

A judge can:

1.  Enter an idea\
2.  See roadmap\
3.  View suggested collaborators\
4.  Watch human team selection

Within 60 seconds.
