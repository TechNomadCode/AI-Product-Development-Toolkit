# Interactive PRD Creation Prompt for LLMs

This document describes a prompt template designed to guide Large Language Models (LLMs) like Google Gemini or similar advanced conversational AI through an interactive process of creating a draft Product Requirements Document (PRD).

## Description

Creating a comprehensive PRD can be challenging, often starting with a blank page or scattered notes. This prompt template leverages the conversational and analytical capabilities of LLMs to turn an initial "brain dump" of ideas into a structured set of requirements through guided questioning. When you use this prompt, the AI acts as a Product Manager assistant, asking clarifying questions, ensuring coverage, and seeking your confirmation to collaboratively build the PRD draft.

## Why Use This Prompt?

*   **Overcomes Blank Page Syndrome:** Start with your raw ideas, and let the AI help structure them.
*   **Ensures Thoroughness:** The prompt guides the AI to ask clarifying questions, consider different perspectives, and check for inconsistencies.
*   **Structured Thinking:** Transforms scattered thoughts into organized PRD sections (Goals, Users, User Stories, Requirements, etc.).
*   **User-Centered Flow:** Includes explicit check-ins where the AI verifies its understanding and direction with you.
*   **Reduces Initial Drafting Time:** Speeds up the creation of the *first draft* of your PRD.

## Key Features of the Prompt's Design

*   **Brain Dump Input:** Starts with your unstructured notes and ideas.
*   **Guided Questioning:** Instructs the AI to analyze your input and ask targeted questions to elicit details.
*   **Iterative Process:** Designed for building the PRD section by section through conversation.
*   **Rule-Based Guidance:** Incorporates principles for clarity, step-by-step reasoning, cross-referencing, and assumption validation.
*   **User Confirmation Checkpoints:** Instructs the AI to regularly check if its interpretation and proposed direction align with your vision.
*   **Structured Output Goal:** Aims to gather information needed for a standard PRD format.

## How to Use the Prompt

1.  **Copy the Prompt Text:** Obtain the full prompt template text.
2.  **Fill the Brain Dump:** Replace the placeholder `[ <<< PASTE YOUR RAW NOTES, IDEAS, CONTEXT, GOALS, FEATURES, PROBLEMS, ETC. HERE >>> ]` within the `--- BRAINDUMP START ---` and `--- BRAINDUMP END ---` markers with your actual notes. Be as detailed or as brief as you currently are.
3.  **Fill Placeholders:** Update the bracketed information like `[mention general product type if known]` and `[Mention any major known constraints if you have them]` under the "TONE & CONSTRAINTS" section, or remove them if not applicable.
4.  **Paste into AI:** Copy the entire modified prompt and paste it into your chat interface with a capable LLM (like Gemini, GPT-4, Claude 3, etc.).
5.  **Engage:** Answer the AI's questions thoughtfully. Your responses will guide the subsequent questions.
6.  **Iterate:** Continue the conversation, providing feedback and answers until you feel enough information has been gathered for a solid draft. The AI should offer to compile the draft based on your conversation.

## Customizing Your Use of the Prompt

*   **Brain Dump:** This section *must* be customized with your specific product ideas.
*   **Constraints/Product Type:** Update these placeholders for context relevant to your project.
*   **Process Rules (Advanced):** While designed to be robust, you could potentially tweak the rules in the `PROCESS & KEY RULES` section if you have specific needs, but do so cautiously as it might affect the guidance quality.

## Model Compatibility

*   This prompt was developed with models like **Google Gemini** in mind (large context window, tweakable parameters).
*   **Context Window:** Models with a **large context window (high token limit)** are strongly preferred. The interactive nature of this prompt leads to lengthy conversations, and the AI needs to retain the context from earlier parts of the discussion to ask relevant follow-up questions and generate a coherent final document.
*   **Parameter Tuning:** For best results when the AI generates the final PRD draft (less critical during the questioning phase), using **low temperature** (e.g., 0.2-0.5) and **high Top-P** (e.g., 0.9-1.0) is recommended to encourage factual, focused output.

## Important Considerations

*   **AI is an Assistant, Not the Author:** The output is a *draft*. It helps organize thoughts and generate initial text.
*   **CRITICAL Human Review Required:** The generated PRD draft **MUST** be thoroughly reviewed, edited, corrected, and validated by product managers, engineers, designers, and relevant stakeholders. AI can miss nuances, make incorrect assumptions, or hallucinate requirements.
*   **Input Quality Matters:** The detail and clarity of your initial brain dump and subsequent answers significantly impact the quality of the AI's questions and the final draft.
*   **Iterative Process:** Don't expect a perfect PRD in one go. Use the AI to explore ideas and structure, then refine manually.