# Session Continuation and Context Distillation Prompt for LLMs

This document describes a meta-instruction prompt that distills a long chat history into a single, structured session state document (`project_plan_continuation.md`) for starting a fresh chat.

**Start here:** copy the [prompt in port.md](./port.md) into your current conversation while the needed history is still available. It cannot recover messages the model no longer has access to.

## Description

Long AI development sessions accumulate token bloat and context noise. This prompt directs the LLM to analyze the entire chat history and output a consolidated project plan. It captures original guidelines, new rules derived from your corrections, technical learnings, supervisor action items, and an updated task list so you can resume work in a clean session without losing context.

## Why Use This Prompt?

*   **Creates a Shorter Handoff:** Summarizes available project history for a fresh chat; review it for missing or incorrect details.
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

Use a conversational model with access to the project history you want to summarize. Check the extracted facts against your files and decisions before starting the next session.

## Important Considerations

*   **Review Required:** Quickly verify the extracted tasks and rules before starting the new session.
*   **Quality Depends on History:** Clearer feedback during the original chat produces better extracted rules.
