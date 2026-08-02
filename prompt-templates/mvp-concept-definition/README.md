# Interactive MVP Concept Definition Prompt for LLMs

This document describes a prompt template designed to guide Large Language Models (LLMs) through an interactive process of defining a focused Minimum Viable Product (MVP) Concept.

## Description

Defining a clear MVP concept is the crucial first step before planning development. This prompt template uses an LLM as a Lean Startup Advisor to help structure this definition process. Starting with your broader Product Requirements Document (PRD) and optional UX Specifications, the AI asks targeted questions to help you collaboratively define the MVP's core hypothesis, target audience subset, specific problem, minimum required features (In/Out), and key constraints, ensuring alignment with your overall vision.

## Why Use This Prompt?

*   **Bridges Vision to MVP:** Helps translate a broad product vision (from PRD/UX) into a specific, actionable MVP concept.
*   **Ensures Focus:** Guides you to identify the single most important hypothesis to test first.
*   **Leverages Existing Work:** Explicitly designed to use your PRD and UX Specs as source material, avoiding redundant effort and ensuring continuity.
*   **Structured Concept Definition:** Transforms potentially vague initial ideas into a clearly structured MVP Concept Description.
*   **Prioritization Aid:** Facilitates the difficult process of deciding what *not* to build for the initial MVP.
*   **Reduces "Manual Step" Friction:** Turns the often-manual process of defining the MVP scope into a guided, interactive exercise.

## Key Features of the Prompt's Design

*   **Contextual Input:** Takes the full PRD (required) and optional UX Specifications as primary context.
*   **Leverages Documentation:** Instructs the AI to actively reference and use the provided documents to guide the conversation.
*   **Scope Narrowing Focus:** Questions are designed to help select, prioritize, and refine elements *from* the existing documentation for the MVP.
*   **Non-Redundant Questioning:** Aims to avoid asking for information already clearly present in the input documents.
*   **Iterative Q&A:** Builds the MVP concept definition through a step-by-step conversational process.
*   **User Confirmation Checkpoints:** Ensures alignment on the hypothesis, audience, features, etc., before finalizing the concept.
*   **Structured Output:** Produces a clear MVP Concept Description ready for input into MVP planning prompts.

## How to Use the Prompt

1.  **Copy the Prompt Text:** Obtain the full prompt template text.
2.  **Paste PRD:** Replace the placeholder within `--- PRD START ---` and `--- PRD END ---` with the full text of your existing PRD.
3.  **Paste UX Specs (Optional):** Replace the placeholder within `--- UX SPECS START ---` and `--- UX SPECS END ---` with relevant UX specs, or indicate if not providing.
4.  **Add Initial Thoughts:** Replace the placeholder within `--- INITIAL THOUGHTS START ---` and `--- INITIAL THOUGHTS END ---` with your preliminary ideas about the first version.
5.  **Fill Placeholders:** Update any bracketed information under "TONE & CONSTRAINTS" if applicable.
6.  **Paste into AI:** Copy the entire modified prompt and paste it into your chat interface with a capable LLM.
7.  **Engage:** Answer the AI's questions thoughtfully, focusing on prioritizing and narrowing the scope based on your PRD/UX.
8.  **Iterate:** Continue the conversation until the MVP concept feels well-defined and focused.

## Customizing Your Use of the Prompt

*   **Inputs:** The PRD and Initial Thoughts sections *must* be filled. UX Specs are optional but recommended for feature discussions.
*   **Constraints:** Update the placeholder under TONE & CONSTRAINTS if you have specific MVP-level constraints known upfront.

## Model Compatibility

*   This prompt was developed with models like **Google Gemini** in mind (large context window, tweakable parameters).
*   **Context Window:** Models with a **large context window (high token limit)** are strongly preferred, as the AI needs to reference the potentially lengthy PRD and UX Specs throughout the conversation.
*   **Parameter Tuning:** Standard conversational parameters are generally suitable. Low temperature might help keep the focus grounded in the provided documents if needed.

## Important Considerations

*   **AI is an Assistant:** The output is a *draft* MVP concept. It helps structure strategic thinking.
*   **Human Strategy Required:** Defining the MVP hypothesis and scope is a critical strategic decision. The AI facilitates, but **YOU** make the final calls based on your business goals and market understanding.
*   **Input Quality Matters:** The clarity and completeness of your PRD, UX Specs, and initial thoughts directly influence the quality of the guided conversation and the resulting concept.
*   **Concept is a Starting Point:** The defined MVP concept is the input for the next stage: detailed MVP planning or build specification.