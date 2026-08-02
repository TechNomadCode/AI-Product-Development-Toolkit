# Interactive Test Plan Outline Prompt for LLMs

This document describes a prompt template designed to guide Large Language Models (LLMs) through an interactive process of creating a draft Test Plan Outline.

## Description

Defining a clear test plan is crucial for ensuring software quality. This prompt template uses an LLM as an experienced QA Lead to help structure this planning process. Starting with the scope of features or requirements to be tested, the AI asks targeted questions to collaboratively define the testing objectives, scope (in/out), features under test, testing types, environments, execution strategy, and success criteria.

## Why Use This Prompt?

*   **Structured Test Planning:** Guides you through the essential components of a comprehensive test plan.
*   **Clear Scope Definition:** Helps explicitly define what is and isn't being tested in a given cycle.
*   **Comprehensive Coverage:** Prompts consideration of various testing types (functional, usability, performance, etc.).
*   **Risk Consideration:** Facilitates thinking about potential risks to the testing process.
*   **Defines Success:** Helps establish clear entry and exit criteria for testing phases.
*   **User-Centered Flow:** Includes check-ins to ensure the plan aligns with your project's needs.

## Key Features of the Prompt's Design

*   **Scope Input:** Takes the specific features/requirements/user stories to be tested as primary input.
*   **Contextual Guidance:** Instructs the AI to analyze the scope and ask relevant planning questions.
*   **Logical Flow:** Structures the conversation from scope definition through testing types, environments, execution, and criteria.
*   **Iterative Questioning:** Builds the test plan outline through a step-by-step Q&A process.
*   **User Confirmation Checkpoints:** Ensures alignment before moving to new planning sections.
*   **Focus on Outline:** Aims to create a structured outline, not necessarily fully detailed test cases.

## How to Use the Prompt

1.  **Copy the Prompt Text:** Obtain the full prompt template text.
2.  **Fill Scope Input:** Replace the placeholder within `--- SCOPE START ---` and `--- SCOPE END ---` with the specific features, requirements, or user stories to be tested in this cycle. Optionally add context from PRDs etc.
3.  **Fill Placeholders:** Update any bracketed information under "TONE & CONSTRAINTS" (e.g., known constraints like limited time or resources).
4.  **Paste into AI:** Copy the entire modified prompt and paste it into your chat interface with a capable LLM.
5.  **Engage:** Answer the AI's questions thoughtfully to build out the test plan details.
6.  **Iterate:** Continue the conversation until the core elements of the test plan outline feel sufficiently defined.

## Customizing Your Use of the Prompt

*   **Scope Input:** This section *must* be filled with the specific items under test for this plan.
*   **Constraints:** Update these placeholders for accuracy regarding your testing environment.
*   **Optional Sections:** Guide the AI to skip or briefly cover optional sections (Tools, Schedule) if not needed for this outline.

## Model Compatibility

*   This prompt was developed with models like **Google Gemini** in mind (large context window, tweakable parameters).
*   **Context Window:** Models with a **large context window (high token limit)** are strongly preferred. The interactive nature of this prompt leads to lengthy conversations, and the AI needs to retain the context from earlier parts of the discussion to ask relevant follow-up questions and generate a coherent final document.
*   **Parameter Tuning:** For best results when the AI generates the final PRD draft (less critical during the questioning phase), using **low temperature** (e.g., 0.2-0.5) and **high Top-P** (e.g., 0.9-1.0) is recommended to encourage factual, focused output.

## Important Considerations

*   **AI is an Assistant:** The output is a *draft* test plan outline. It helps structure the planning but doesn't replace QA expertise.
*   **Human Expertise Required:** The generated outline **MUST** be reviewed, refined, and detailed (e.g., writing specific test cases) by experienced QA personnel or the project team. AI cannot fully assess risk or design effective tests alone.
*   **Input Quality Matters:** The clarity and completeness of the scope definition significantly impact the quality of the resulting plan outline.
*   **Plan is a Living Document:** The test plan outline is a starting point and should be updated as requirements change or issues are discovered during testing.