# TripOps AI

**Agentic Travel Operations Automation Platform**  
*Project status: In Progress — initial planning and repository setup*

TripOps AI is a learning and portfolio project exploring how agentic AI can streamline travel-agency operations. The planned workflow covers customer enquiry intake, retrieval over supplier documents, quotation preparation, human approval, and post-booking task tracking.

> **Current status:** This repository is a starter scaffold. The application features below are planned and are not implemented yet.

## Project goals

- Convert natural-language travel enquiries into validated, structured trip requirements.
- Retrieve relevant information from sample hotel contracts, supplier rate sheets, cancellation policies, and destination guides using RAG.
- Prepare draft itineraries and quotations using deterministic pricing functions.
- Use tool-calling agents for controlled business workflows, with human approval before external actions.
- Demonstrate safe browser automation against a local mock booking site, not live airline or supplier systems.
- Evaluate extraction, retrieval, groundedness, pricing, tool selection, and workflow reliability with repeatable test cases.

## Planned technology

- **Backend:** Python, FastAPI, Pydantic
- **Agent orchestration:** LangGraph, OpenAI API (provider abstraction planned)
- **Retrieval:** PostgreSQL, pgvector
- **Workflow support:** Redis (as needed), Playwright for local mock-browser automation
- **Frontend:** React, TypeScript
- **Testing & evaluation:** pytest and a custom evaluation harness; optional RAGAS/LangSmith integration
- **Development:** Docker, GitHub Actions

## Planned architecture

```text
Customer enquiry
      |
      v
FastAPI API + validation
      |
      v
LangGraph workflow orchestrator
  |          |            |
  v          v            v
Enquiry     RAG       Quotation
agent       agent     tools
  |          |            |
  +----------+------------+
             |
             v
     Human approval gate
             |
             v
 Post-booking task workflow
             |
             v
 PostgreSQL / pgvector

Local mock booking site <--> Playwright automation
Evaluation harness --> quality, accuracy, and reliability reports
```

## Planned MVP milestones

1. **Enquiry intake:** define request schemas, validation, and structured extraction tests.
2. **Knowledge retrieval:** ingest synthetic supplier documents and implement cited retrieval.
3. **Quotation workflow:** add deterministic pricing tools and PDF draft generation.
4. **Agent orchestration:** connect the workflow with LangGraph, state handling, and approval gates.
5. **Evaluation:** create a repeatable dataset and report extraction, retrieval, groundedness, pricing, and tool-call metrics.
6. **Browser automation:** build a local mock booking interface and test Playwright actions, retries, and audit logs.
7. **Frontend & deployment:** add a React interface, containerize the services, and document deployment.

## Repository structure

```text
tripops-ai/
├── backend/
│   ├── app/
│   │   ├── agents/
│   │   ├── api/
│   │   ├── core/
│   │   └── services/
│   └── tests/
├── automation/
├── docs/
├── evals/
│   ├── datasets/
│   └── results/
├── frontend/
├── .gitignore
└── README.md
```

## Responsible-use boundaries

- Use synthetic customer, passenger, booking, and supplier data during development.
- Keep API keys in environment variables; never commit secrets or real personal data.
- Require explicit human approval before sending quotations or taking consequential booking actions.
- Run browser automation against a local mock website for demonstrations and tests.
- Show source references for document-grounded answers and clearly flag missing or uncertain information.

## Development

Implementation instructions will be added as the MVP is built. The initial repository contains the project plan and directory scaffold only.

## License

No license has been selected yet. Until one is added, all rights are reserved by the author.
