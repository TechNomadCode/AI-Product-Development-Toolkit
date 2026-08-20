# Guided User Research Questionnaire Prompt for LLMs

This directory contains a prompt template for turning a product research brief into a ready-to-field user questionnaire through guided conversation.

## Description

Questionnaires often start as a list of questions instead of a clear research decision. This template asks an LLM to clarify what the team needs to learn, who should respond, and how the findings will be used before drafting the questionnaire. It then builds a structured survey with screening, current behavior, scenario exploration, attitudes, and willingness-to-pay sections.

The prompt is suitable for early product discovery, concept validation, and follow-up research. It can be adapted for general products or AI-enabled products without assuming that every study needs the same questions or sample size.

## Why Use This Prompt?

*   **Starts With the Decision:** Connects every section to a research objective, hypothesis, or product decision.
*   **Reduces Leading Questions:** Separates current behavior from reactions to a proposed concept and asks for neutral wording.
*   **Supports Useful Branching:** Defines eligibility, termination, and follow-up logic so respondents only see relevant questions.
*   **Makes the Draft Field-Ready:** Requires question IDs, response types, answer options, and required or optional status.
*   **Plans for Response Quality:** Includes pretesting, sample planning, and explicit rules for flagging low-quality responses.
*   **Keeps Human Review in the Loop:** Uses confirmation checkpoints before changing sections or finalizing the questionnaire.

## What the Final Draft Covers

1.  Research objective and sample plan.
2.  Screener and relevant respondent profile.
3.  Current behavior and tool usage.
4.  Core scenario deep dive.
5.  Attitudes, adoption barriers, and willingness to pay.
6.  Open feedback and optional follow-up consent.
7.  Branching map, section rationale, and response-quality checks.

## How to Use the Prompt

1.  Copy [`Guided-User-Research-Questionnaire.md`](./Guided-User-Research-Questionnaire.md).
2.  Replace the placeholder in `RESEARCH BRIEF` with your product context, target audience, decision to make, and known constraints.
3.  Paste the adapted prompt into a capable conversational LLM.
4.  Answer the model's clarifying questions and confirm the proposed research plan.
5.  Review the final draft with the product owner and, where appropriate, a user researcher or privacy stakeholder.
6.  Pilot the questionnaire with a small group before broad distribution, then revise unclear wording or broken branching.

## Example Research Brief

> We are exploring a fictional AI writing assistant for freelance writers. We need to decide whether an early version should prioritize first-draft generation or revision support. We want to learn about respondents' recent writing workflows, current tools, unmet needs, adoption concerns, and reactions to a clearly described paid concept. The questionnaire should take no more than eight minutes and should not collect names or client information.

This example is intentionally fictional. Replace it with your own context, and remove any confidential, personal, or unnecessary information before sharing it with an external model.

## Model Compatibility

*   Use a conversational LLM that can retain the research brief and confirmed decisions across a multi-step discussion.
*   A larger context window is helpful for long briefs, but the template does not depend on a specific model, survey platform, or proprietary tool.

## Important Considerations

*   **A Questionnaire Is Not Always the Right Method:** Exploratory or sensitive questions may require interviews, observation, or another method. The prompt asks the model to flag this limitation instead of forcing every objective into a survey.
*   **Sample Size Is Context-Dependent:** Define it from the target population, required segments, expected incidence, decision risk, and desired precision. Do not treat one universal number as valid for every study.
*   **Stated Intent Is Not Actual Behavior:** Willingness-to-pay answers indicate stated preference and should not be presented as proven demand or revenue.
*   **Collect the Minimum Necessary Data:** Avoid sensitive or identifying fields unless they are essential, justified, and handled with appropriate consent.
*   **Human Review Is Required:** Check wording, answer coverage, accessibility, branching, privacy, and analysis readiness before launch.
