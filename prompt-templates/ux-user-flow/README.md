# Interactive UX & User Flow Documentation Prompt for LLMs

This document describes a prompt template designed to guide Large Language Models (LLMs) like Google Gemini, or similar advanced conversational AI through an interactive process of creating comprehensive UX & UI specifications that bridge the gap between product requirements and frontend implementation.

## Description

Creating effective user experience documentation requires translating abstract product requirements into concrete visual and interaction specifications. This prompt template leverages the conversational and analytical capabilities of LLMs to turn a Product Requirements Document (PRD) into structured UX specifications through guided questioning. When you use this prompt, the AI acts as a UX Designer and Frontend Design Strategist, asking clarifying questions about layouts, user flows, and interaction patterns to collaboratively build comprehensive frontend specifications.

## Why Use This Prompt?

* **Bridges the PRD-to-Development Gap:** Transforms functional requirements into implementation specifications that developers and designers can directly work from.
* **Ensures Comprehensive Coverage:** The prompt guides the AI to ask clarifying questions about all aspects of the user experience, from information architecture to interaction patterns.
* **User-Centered Development:** Incorporates explicit check-ins where the AI verifies its understanding of your vision at critical points.
* **Visual Communication:** Helps visualize interfaces and user flows using text-based layout sketches and descriptions.
* **v0.dev Integration:** Includes a dedicated section that formats your UX specifications for direct use with v0.dev or similar AI design tools.

## Key Features of the Prompt's Design

* **PRD-Based Starting Point:** Begins with your existing Product Requirements Document to ensure alignment with product goals.
* **Guided Questioning:** Instructs the AI to analyze the PRD and ask targeted questions about translating requirements into visual interfaces.
* **Visualization Techniques:** Incorporates text-based layout descriptions and component hierarchies that help illustrate interface concepts.
* **Iterative Process:** Designed for building UX specifications section by section through conversation.
* **User Confirmation Checkpoints:** Requires the AI to regularly verify that its interpretation aligns with your vision.
* **v0.dev Design Translation:** Includes a dedicated section that formats your UX specifications for direct use with v0.dev or similar AI design tools.

## How to Use the Prompt

1. **Copy the Prompt Text:** Obtain the full prompt template text.
2. **Insert Your PRD:** Replace the placeholder `[ <<< PASTE YOUR PRODUCT REQUIREMENTS DOCUMENT HERE >>> ]` within the `--- PRD START ---` and `--- PRD END ---` markers with your actual Product Requirements Document.
3. **Add Constraints:** Update the bracketed information under the "TONE & CONSTRAINTS" section with any specific design system requirements, device support needs, or accessibility standards.
4. **Paste into AI:** Copy the entire modified prompt and paste it into your chat interface with a capable LLM (like Gemini, GPT-4, Claude 3, etc.).
5. **Engage:** Answer the AI's questions thoughtfully about how requirements translate to visual interfaces and user flows. Your responses will guide the subsequent questions.
6. **Iterate:** Continue the conversation, providing feedback and answers until you feel enough information has been gathered for comprehensive UX specifications.
7. **Review the v0.dev Translation:** Pay special attention to the v0.dev Design Translation Guide section, as this can be directly used as input for AI-powered visual design tools.

## Model Compatibility

* This prompt was developed with models like Google Gemini, Claude 3, and GPT-4 in mind.
* **Context Window:** Models with a **large context window (high token limit)** are strongly preferred. The interactive nature of this prompt leads to lengthy conversations that include both the original PRD and the evolving UX specifications.
* **Parameter Tuning:** For best results, using **moderate temperature** (0.5-0.7) is recommended to balance creative suggestions with concrete specifications.

## Important Considerations

* **AI is an Assistant, Not the Expert:** The output is a collaborative draft. It helps organize thoughts and generate initial specifications.
* **CRITICAL Human Review Required:** The generated UX & User Flow specification **MUST** be thoroughly reviewed, edited, and validated by UX designers, product managers, and engineers.
* **Input Quality Matters:** The detail and clarity of your PRD and subsequent answers significantly impact the quality of the resulting UX specification.
* **Iterative Process:** Don't expect perfect UX specifications in one session. Use the AI to explore ideas and structure, then refine as needed.
* **Visual Testing Required:** The text-based layout descriptions should be tested with actual visual prototypes before implementation.
* **v0.dev Guidance Only:** The v0.dev translation section provides guidance, but you may need to adjust the output based on your specific design needs.
