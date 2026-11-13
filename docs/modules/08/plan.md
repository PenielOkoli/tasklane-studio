# Module 8 implementation plan

Continue Tasklane Agent from `09208ac` in a separate repository and GitHub-connected Vercel project. The inherited Agent, Knowledge and Board views remain accessible.

1. Define a release-review brief and separate Research, Design and Testing assignments. Show the handoff packets each recipient receives. Design and Testing both receive the same Research output and work independently from each other.
2. Compare scope, recommendations, evidence and unknowns. Require the project lead to record a choice and rationale before the synthesis step opens.
3. Give synthesis the role outputs and the recorded decision. Display the human decision directly from the verified record and show what to do next, who owns it, and what remains unresolved.
4. Verify live model calls separately from the labeled practice walkthrough. Check stale checkpoints, rejected premature decisions, citation scope, failure recovery and export.

Each checkpoint advances one bounded model call. Research uses selected fictional Tasklane passages. Roles use separate prompts and outputs. The orchestration code routes typed handoff packets, following the idea of passing scoped context described in the [OpenAI Agents SDK handoff guide](https://openai.github.io/openai-agents-js/guides/handoffs/). This implementation uses AI SDK and Groq.
