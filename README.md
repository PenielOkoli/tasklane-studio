# Tasklane Studio

FlexiSAF Module 8, Multi-Agent and Role-Based Workflow Interfaces. Tasklane Studio helps a project lead compare recommendations from three specialists before deciding what should happen next.

- [Live Vercel app](https://tasklane-studio.vercel.app/)
- [Reviewer walkthrough and status](docs/modules/08/submission.md)
- [Assessment mapping](docs/modules/08/assessment.md)
- [Implementation plan](docs/modules/08/plan.md)

## Workflow

Researcher reviews the brief and selected fictional project excerpts. Designer and Tester receive that research handoff in separate calls and each produce a position, rationale, uncertainty and evidence references. The UI compares the positions. The project lead records a decision and reason. A separate synthesis call suggests the next action, proposed owner and open risk. The recorded human decision is displayed directly from the saved checkpoint.

The roles use the same configured model with distinct assignments and limited context. The application owns handoff order and verifies inputs. The release review changes no board tasks. The inherited Agent, Knowledge and Board views are available from Studio.

## When multiple roles help

Use this workflow when people need to see the tradeoff between different responsibilities. In a release review, Research can flag a small sample, Design can propose a pilot, and Testing can call out unverified release gates. Separating their outputs makes it possible to inspect the evidence and explain why the lead chose one path. For a source lookup, a small copy edit or a routine task update, a single assistant is usually enough. Extra model calls add latency and cost, and roles using one model can share its mistakes.

## Run locally

Use Node 22. Run `npm ci`, set a unique `SESSION_SECRET` of at least 32 characters in the server environment, optionally set `GROQ_API_KEY` for live AI and run `npm run dev`. Keep credentials server-only. For checks, run `npm run check`. Run `node --import tsx scripts/verify-studio.ts <origin>` for HTTP checks. Add `--ai` to exercise all four model calls.

Practice uses a fixed sample brief and labeled example outputs. Live recommendations can vary. Source IDs are checked against each role’s context. Their presence does not establish that the passage supports every claim. Review data is saved in encrypted cookies for up to 24 hours and can be exported. Use one tab at a time. A new review replaces the saved review. The demo has no shared audit database or global replay protection.

## Continuity

Continues Tasklane Agent from `09208ac` in a separate repository and Vercel project. The Tasklane product follows the earlier continuity decision documented in the internship tracker.
