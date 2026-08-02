# Session Continuation and Context Distillation Prompt for LLMs

This document describes a meta-instruction prompt that distills a long chat history into a single, structured session state document (`project_plan_continuation.md`) for starting a fresh chat.

## Description

Long AI development sessions accumulate token bloat and context noise. This prompt directs the LLM to analyze the entire chat history and output a consolidated project plan. It captures original guidelines, new rules derived from your corrections, technical learnings, supervisor action items, and an updated task list so you can resume work in a clean session without losing context.

## Why Use This Prompt?

*   **Resets Context Window:** Eliminates chat bloat while preserving 100% of project progress.
*   **Extracts Learned Rules:** Converts real-time corrections into forward-looking guidelines.
*   **Preserves Technical Directives:** Saves discovered API details, data structures, and setup facts.
*   **Enables Clean Hand-Offs:** Makes it easy to start a fresh chat or switch AI tools.

## Key Features of the Prompt's Design

*   **Self-Analysis:** Instructs the LLM to evaluate past corrections and derive new rules.
*   **Structured 5-Part Output:** Generates guidelines, current state, technical facts, supervisor checklist, and remaining tasks.
*   **Zero-Chat Output:** Produces clean markdown ready to copy directly into a new chat.

## How to Use the Prompt

1. **Paste Prompt:** Run the meta-instruction at the end of your chat session.
2. **Copy Output:** Copy the generated `project_plan_continuation.md` text.
3. **Start New Chat:** Open a fresh chat session.
4. **Resume:** Paste the continuation document as your first message to restore context.

## Model Compatibility

*   **Models:** Requires long-context, instruction-following models (e.g., Claude 3.5 Sonnet, GPT-4o, Gemini 1.5 Pro).
*   **Parameters:** Use **low temperature** (0.1–0.3) for accurate, factual extraction.

## Important Considerations

*   **Review Required:** Quickly verify the extracted tasks and rules before starting the new session.
*   **Quality Depends on History:** Clearer feedback during the original chat produces better extracted rules.