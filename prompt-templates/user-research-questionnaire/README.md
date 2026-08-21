# Guided User Research Questionnaire Prompt for LLMs

This directory contains two prompt templates for turning a product research brief into an implementation-ready questionnaire draft, then turning collected responses into structured PRD Research Input.

## Description

Questionnaires often start as a list of questions instead of a clear research decision. The questionnaire-design prompt asks an LLM to clarify what the team needs to learn, who should respond, and how the findings will be used before drafting the questionnaire. It then builds a structured survey with essential screening, current behavior, scenario exploration, attitudes, and willingness-to-pay sections, while keeping sensitive profile questions near the end.

After the questionnaire is implemented and responses are collected, the post-research prompt analyzes the evidence, separates observed findings from interpretations and unsupported assumptions, and prepares a structured handoff for PRD generation.

The prompts are suitable for early product discovery, concept evaluation, and follow-up research. They can be adapted for general products or AI-enabled products without assuming that every study needs the same questions or sample size.

## Why Use These Prompts?

*   **Starts With the Decision:** Connects every section to a research objective, hypothesis, or product decision.
*   **Reduces Leading Questions:** Separates current behavior from reactions to a proposed concept and asks for neutral wording.
*   **Separates Screening From Profiling:** Keeps essential eligibility questions at the start and sensitive profile questions near the end.
*   **Supports Useful Branching:** Defines eligibility, termination, and follow-up logic so respondents only see relevant questions.
*   **Makes the Draft Implementation-Ready:** Requires question IDs, response types, answer options, and required or optional status.
*   **Plans for Response Quality:** Includes pretesting, sample planning, and explicit rules for flagging low-quality responses.
*   **Creates an Evidence-Led Handoff:** Produces PRD Research Input with traceable findings, confidence levels, open assumptions, and recommendations.
*   **Keeps Human Review in the Loop:** Uses confirmation checkpoints before changing sections or finalizing the questionnaire.

## What the Workflow Covers

1.  Research objective and sample plan.
2.  Essential eligibility screeners.
3.  Current behavior and tool usage.
4.  Core scenario deep dive.
5.  Attitudes, adoption barriers, and willingness to pay.
6.  Open feedback.
7.  Sensitive profile questions near the end, when justified, followed by separate optional follow-up consent.
8.  Branching map, section rationale, and response-quality checks.
9.  Post-research findings and structured PRD Research Input.

## Workflow Handoff

Use the templates as a sequence:

`research brief -> questionnaire -> collected responses -> research findings -> PRD Research Input -> PRD`

The questionnaire is an implementation-ready draft, not research evidence. Implement and pilot it in an appropriate survey tool, collect responses under the confirmed consent and privacy plan, and complete response-quality review before generating findings. The post-research output should then be reviewed by the research and product owners before it is used to inform PRD goals or requirements.

## How to Use the Prompts

1.  Copy [`Guided-User-Research-Questionnaire.md`](./Guided-User-Research-Questionnaire.md).
2.  Replace the placeholder in `RESEARCH BRIEF` with your product context, target audience, decision to make, and known constraints.
3.  Paste the adapted prompt into a capable conversational LLM.
4.  Answer the model's clarifying questions and confirm the proposed research plan.
5.  Review the final draft with the product owner and, where appropriate, a user researcher or privacy stakeholder.
6.  Pilot the questionnaire with a small group before broad distribution, then revise unclear wording or broken branching.
7.  Implement the approved questionnaire in a survey tool, field it, and complete the planned response-quality review.
8.  Remove direct identifiers, then copy [`Post-Research-PRD-Input.md`](./Post-Research-PRD-Input.md) and provide the research brief, final questionnaire and codebook, collection notes, quality or exclusion log, and collected responses or approved analysis tables.
9.  Review the resulting findings, confidence levels, and unsupported assumptions with the research and product owners.
10. Paste the approved `PRD Research Input` section into the `MY INITIAL BRAINDUMP` section of the [`prd-generation` prompt](../prd-generation/prd-generation.md), preserving its evidence references and limitations.

## Example Research Brief

> We are exploring a fictional AI writing assistant for freelance writers. We need to decide whether an early version should prioritize first-draft generation or revision support. We want to learn about respondents' recent writing workflows, current tools, unmet needs, adoption concerns, and reactions to a clearly described paid concept. The questionnaire should take no more than eight minutes and should not collect names or client information.

This example is intentionally fictional. Replace it with your own context, and remove any confidential, personal, or unnecessary information before sharing it with an external model.

## Model Compatibility

*   Use a conversational LLM that can retain the research brief and confirmed decisions across a multi-step discussion.
*   A larger context window is helpful for long briefs, but the templates do not depend on a specific model, survey platform, or proprietary tool.

## Important Considerations

*   **A Questionnaire Is Not Always the Right Method:** Exploratory or sensitive questions may require interviews, observation, or another method. The prompt asks the model to flag this limitation instead of forcing every objective into a survey.
*   **Sample Size Is Context-Dependent:** Define it from the target population, required segments, expected incidence, decision risk, and desired precision. Do not treat one universal number as valid for every study.
*   **Stated Intent Is Not Actual Behavior:** Willingness-to-pay answers indicate stated preference and should not be presented as proven demand or revenue.
*   **Collect the Minimum Necessary Data:** Avoid sensitive or identifying fields unless they are essential, justified, and handled with appropriate consent.
*   **Evidence Strength Varies:** A pattern in the collected sample is not automatically representative of the target population. Preserve denominators, limitations, and confidence rationale in the PRD handoff.
*   **Human Review Is Required:** Check wording, answer coverage, accessibility, branching, privacy, and analysis readiness before launch.
