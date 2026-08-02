# Interactive MVP Development Planning Prompt for LLMs

This document describes a prompt template designed to guide Large Language Models (LLMs) through an interactive process of creating a draft Minimum Viable Product (MVP) Development Plan.

## Description

Planning an MVP involves defining *how* to build and test the core product hypothesis efficiently. This prompt template uses an LLM as an expert advisor to help structure this planning process. Starting with your overall Product Requirements Document (PRD) and a specific MVP concept, the AI asks targeted questions to help you define the MVP's scope, features, tech stack, timeline, testing strategy, and success metrics collaboratively.

## Why Use This Prompt?

*   **Structured MVP Planning:** Guides you through the key elements of an MVP development plan.
*   **Leverages Existing PRD:** Uses your full product vision (PRD) as context for focused MVP planning.
*   **Clarifies Scope:** Helps define the absolute minimum features required ("In" vs. "Out").
*   **Considers Technical Aspects:** Integrates discussion of the technology stack logically within the planning flow.
*   **Focuses on Learning:** Emphasizes defining the core hypothesis and success metrics for validation.
*   **User-Centered Flow:** Includes check-ins to ensure the plan aligns with your intent.

## Key Features of the Prompt's Design

*   **Dual Input:** Takes both the full PRD and a specific MVP concept description.
*   **Contextual Guidance:** Instructs the AI to use the PRD contextually while focusing on the MVP specifics.
*   **Logical Flow:** Structures the conversation from MVP goals/features to tech stack, then to execution details (phases, testing, deployment).
*   **Iterative Questioning:** Builds the plan through a step-by-step Q&A process.
*   **User Confirmation Checkpoints:** Ensures alignment before moving to new planning sections.

## How to Use the Prompt

1.  **Copy the Prompt Text:** Obtain the full prompt template text.
2.  **Paste PRD:** Replace the placeholder within `--- PRD START ---` and `--- PRD END ---` with the full text of your existing PRD.
3.  **Fill MVP Concept:** Replace the placeholder within `--- MVP CONCEPT START ---` and `--- MVP CONCEPT END ---` with your specific MVP description (hypothesis, users, minimum features, constraints).
4.  **Fill Placeholders:** Update any bracketed information under "TONE & CONSTRAINTS" (e.g., product type, known constraints).
5.  **Paste into AI:** Copy the entire modified prompt and paste it into your chat interface with a capable LLM.
6.  **Engage:** Answer the AI's questions thoughtfully to build out the plan details.
7.  **Iterate:** Continue the conversation until the plan feels sufficiently detailed for a draft.

## Customizing Your Use of the Prompt

*   **Inputs:** The PRD and MVP Concept sections *must* be filled with your project details.
*   **Constraints:** Update these placeholders for accuracy.
*   **Optional Sections:** You can guide the AI to skip or briefly cover optional sections (Team Roles, Budget) if not needed.

## Model Compatibility

*   This prompt was developed with models like **Google Gemini** in mind (large context window, tweakable parameters).
*   **Context Window:** Models with a **large context window (high token limit)** are strongly preferred. The interactive nature of this prompt leads to lengthy conversations, and the AI needs to retain the context from earlier parts of the discussion to ask relevant follow-up questions and generate a coherent final document.
*   **Parameter Tuning:** For best results when the AI generates the final PRD draft (less critical during the questioning phase), using **low temperature** (e.g., 0.2-0.5) and **high Top-P** (e.g., 0.9-1.0) is recommended to encourage factual, focused output.

## Important Considerations

*   **AI is an Assistant:** The output is a *draft* plan, helping structure thoughts and decisions.
*   **CRITICAL Human Review Required:** The generated plan **MUST** be thoroughly reviewed, validated, and refined by the project team and stakeholders. AI cannot fully grasp real-world complexities or constraints.
*   **Input Quality Matters:** The clarity and detail of your PRD, MVP concept, and answers directly influence the plan's quality.
*   **Plan is a Living Document:** The initial MVP plan will likely evolve as development progresses and learning occurs.