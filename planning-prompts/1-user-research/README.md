# User research prompts

Step 1 of the [planning prompts](../README.md). Two prompts: one designs a questionnaire for your potential users, the other turns their answers into evidence for your PRD. Skip this step if you have no one to ask yet, and start with the [PRD prompt](../2-prd/).

| Prompt | When | You get |
| --- | --- | --- |
| [questionnaire.md](./questionnaire.md) | Before the research | A questionnaire ready to build in a survey tool |
| [research-to-prd.md](./research-to-prd.md) | After you've collected responses | Findings and a `PRD Research Input` section for the PRD prompt |

## What you get

**From the questionnaire prompt:**

- A research plan: the decision, objectives, who qualifies, a sample plan, and what the study can't tell you
- The questionnaire itself, with question IDs, answer types and options, required or optional, and skip logic
- Why each section is there and how to read its answers
- A map of the branches, a pilot plan, and rules for spotting low-quality responses

**From the post-research prompt:**

- An audit of your data: who answered, what's missing, what was excluded
- Findings, interpretations and unsupported assumptions, kept apart, each with an ID and a confidence level
- Prioritized needs and constraints, linked to the evidence
- A `PRD Research Input` section to paste into the [PRD prompt](../2-prd/)

## What to bring

- **For the questionnaire:** a research brief, which goes between `--- RESEARCH BRIEF START ---` and `--- RESEARCH BRIEF END ---`. Say what the product is, the decision you need to make, who you want to hear from, and constraints such as length or data you won't collect. For example:

  > We are exploring a fictional AI writing assistant for freelance writers. We need to decide whether an early version should prioritize first-draft generation or revision support. We want to learn about respondents' recent writing workflows, current tools, unmet needs, adoption concerns, and reactions to a clearly described paid concept. The questionnaire should take no more than eight minutes and should not collect names or client information.

- **For the post-research prompt:** the research brief, the final questionnaire with its question IDs and answer codes, notes on how you collected responses, a list of the responses you excluded and why, and the responses themselves, with names and contact details removed, or your analysis tables.

## How to use them

1. Open [questionnaire.md](./questionnaire.md) and copy it with the copy button at the top right of the file (**Copy raw content**). Replace the example brief with yours.
2. Paste it into a new AI chat and answer its questions. It confirms the research plan with you before it drafts the questionnaire.
3. Try the questionnaire on a few people, fix unclear questions and broken branches, then build it in a survey tool and send it out.
4. Remove names and contact details from the responses. Copy [research-to-prd.md](./research-to-prd.md), fill in its input sections, and paste it into a new chat. It audits the data and asks you questions before it interprets anything.
5. Review the findings, then paste the `PRD Research Input` section into the PRD prompt, in place of the brain dump.

**In Claude Code or Codex?** The `/user-research` [skill](../../README.md#skills) runs either prompt and fills it in from your files.

## Good to know

- A survey isn't always the right method. The prompt says when interviews or another method would answer a question better.
- There's no universal sample size. The prompt plans one from your audience, your decision, and how sure you need to be.
- What people say they'd pay isn't proof they will.
- Collect only the personal data you need, and ask for consent for anything sensitive. Don't paste private information into an AI tool that doesn't need it.
- A pattern in your answers may not hold for everyone. The handoff keeps the counts and limits, so the PRD doesn't overclaim.

## Next step

[PRD](../2-prd/): turn your findings and notes into a product requirements document.

[All planning prompts](../README.md)
