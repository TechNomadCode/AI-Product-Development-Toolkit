# Interactive MVP Build Spec Prompt for LLMs (Ultra-Lean)

This document describes an ultra-lean prompt template designed to guide Large Language Models (LLMs) through an interactive process focused on rapidly defining the core build specification for a Minimum Viable Product (MVP).

## Description

This prompt template prioritizes speed and action, using an LLM as a technical lead to quickly outline *what* needs to be built immediately and *how*. It focuses on defining the essential features and key technology choices for a first functional prototype. While lean, it uses your full Product Requirements Document (PRD) as essential context to ensure the rapid build remains strategically aligned with the overall product vision.

## Why Use This Prompt?

*   **Maximum Speed:** Designed for situations where getting a functional prototype built quickly is the top priority.
*   **Focus on Building:** Centers the conversation entirely on the features to implement and the immediate technical approach.
*   **Core Spec Definition:** Quickly generates an outline of the essential build elements (Purpose, User, Features, Tech).
*   **Strategic Alignment:** Uses the PRD context to ensure the rapid build contributes meaningfully to the larger product goals.
*   **Defers Detailed Planning:** Intentionally skips detailed metrics, testing strategies, timelines, and risk analysis to maintain focus on the build.

## Key Features of the Prompt's Design

*   **Dual Input:** Takes both the full PRD (for context) and a concise MVP concept description (for focus).
*   **Contextual Guidance:** Instructs the AI to use the PRD to ensure strategic alignment while focusing on the immediate build.
*   **Build-Oriented Flow:** Structures the conversation around Purpose -> Features -> Tech Choices.
*   **Direct Questioning:** Encourages fast, specific questions and answers related to implementation.
*   **Lean Output:** Aims for a simple bulleted outline of the core build specification.

## How to Use the Prompt

1.  **Copy the Prompt Text:** Obtain the full prompt template text.
2.  **Paste PRD:** Replace the placeholder within `--- PRD START ---` and `--- PRD END ---` with the full text of your existing PRD.
3.  **Fill MVP Concept:** Replace the placeholder within `--- MVP CONCEPT START ---` and `--- MVP CONCEPT END ---` with your *concise* MVP description (core purpose, user, essential features, key constraints).
4.  **Fill Placeholders:** Update any bracketed information under "TONE & CONSTRAINTS".
5.  **Paste into AI:** Copy the entire modified prompt and paste it into your chat interface with a capable LLM.
6.  **Engage:** Answer the AI's direct questions to quickly define the build spec.
7.  **Iterate Briefly:** Continue until the core build elements (Purpose, User, Features, Tech) are defined.

## Customizing Your Use of the Prompt

*   **Inputs:** The PRD and MVP Concept sections *must* be filled with your project details. The MVP concept should be deliberately concise for this prompt.
*   **Constraints:** Update these placeholders for accuracy.
*   **Optional Tasks:** The "Key Build Tasks" section is optional; focus primarily on Features and Tech.

## Model Compatibility

*   This prompt was developed with models like **Google Gemini** in mind (large context window, tweakable parameters).
*   **Context Window:** Models with a **large context window (high token limit)** are strongly preferred. The interactive nature of this prompt leads to lengthy conversations, and the AI needs to retain the context from earlier parts of the discussion to ask relevant follow-up questions and generate a coherent final document.
*   **Parameter Tuning:** For best results when the AI generates the final PRD draft (less critical during the questioning phase), using **low temperature** (e.g., 0.2-0.5) and **high Top-P** (e.g., 0.9-1.0) is recommended to encourage factual, focused output.

## Important Considerations

*   **Output is a Build Spec, Not a Full Plan:** This prompt generates a starting point for *building*, not a comprehensive project plan. Metrics, detailed testing, timelines, etc., are intentionally deferred.
*   **AI is an Assistant:** The output helps define the initial scope and tech approach quickly.
*   **Human Oversight is Crucial:** The defined spec **MUST** be reviewed and validated by the development team. The AI facilitates decisions; it doesn't replace technical expertise.
*   **Input Quality Matters:** Clear definition of the MVP concept and relevant PRD context are key.
*   **Assumes Iteration:** This approach assumes further planning and refinement will happen alongside or after the initial build.