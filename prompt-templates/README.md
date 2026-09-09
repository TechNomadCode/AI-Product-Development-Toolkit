# Prompt Templates

This directory contains interactive, conversational prompt templates designed to take product ideas from vision to build-ready specifications.

**New here?** Start with the [PRD prompt](./prd-generation/prd-generation.md) and its [usage guide](./prd-generation/README.md). Each folder below explains what to paste into its prompt and what to expect next.

## Guided Conversational Approach

What makes these prompts unique is their **user-centered, guided conversational design**:

*   **Interactive Process:** Rather than one-shot prompting, these templates guide AI models through an iterative conversation with you.
*   **Structured Questioning:** The AI asks targeted questions focused on specific aspects of your project, building a comprehensive document piece by piece.
*   **User Confirmation Checkpoints:** The prompts explicitly instruct the AI to verify its understanding and direction with you before moving to new sections or making significant interpretations.
*   **Contextual Analysis:** Templates use inputs from previous steps (like a PRD for context plus an MVP concept), instructing the AI to cross-reference information for consistency.
*   **Adaptive Guidance:** The templates help you think through aspects you might have missed, while allowing you to maintain control over the final direction.

## Template Index

*   [user-research-questionnaire](./user-research-questionnaire/): Templates for designing an implementation-ready user research questionnaire and turning collected responses into evidence-linked PRD Research Input.
*   [prd-generation](./prd-generation/): Template for creating comprehensive Product Requirements Documents.
*   [ux-user-flow](./ux-user-flow/): Template for translating PRDs into detailed UX Specifications.
*   [mvp-concept-definition](./mvp-concept-definition/): Template for defining focused MVP scope, hypotheses, and features.
*   [mvp-development-planning](./mvp-development-planning/): Template for developing detailed MVP development plans based on the concept.
*   [ultra-lean-mvp-development-planning](./ultra-lean-mvp-development-planning/): Template for developing detailed Ultra Lean MVP development plans based on the concept
*   [test-plan-generation](./test-plan-generation/): Template for creating thorough test plans for software quality assurance.
*   [v0-design-prompts](./v0-design-prompts/): Templates for generating `v0.dev` prompts based on UX Specs and MVP scope.
*   [session-continuation](./session-continuation/): Meta-prompt for distilling long chat sessions into continuation plans.

## How to Use Prompt Templates

1.  **Browse:** Navigate to the relevant subfolder for the step you are on.
2.  **Copy & Adapt:** Copy the prompt text from the `.md` file. Replace all placeholders like `[ <<< PASTE ... HERE >>> ]` or `[example]` with your specific project details.
3.  **Engage:** Paste the adapted prompt into your AI tool. Answer the AI's questions thoughtfully - your responses guide the process.
4.  **Confirm:** Pay attention to the AI's check-in points to ensure the output stays aligned with your vision.
5.  **Iterate:** Continue the conversation until the desired document or plan is drafted.

## Model Compatibility

Use a conversational model that can retain your inputs and confirmed decisions throughout the exchange. The templates are plain text, but output quality varies by model and task; review the draft before using it. The subfolder guides explain any additional setup.
