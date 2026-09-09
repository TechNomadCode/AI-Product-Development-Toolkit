# AI Product Development Toolkit

**Free prompts and agent rules for building software with AI:** clarify what to build, keep the work focused, and carry project decisions into the next session.

Copy a prompt into your AI chat, answer its questions, and review the resulting specification or handoff. The templates are Markdown files; you can use them without cloning this repository or installing a package.

## Start here

| What you need | Open this | What to bring | What you get |
| --- | --- | --- | --- |
| Turn an app idea into clear requirements | [PRD prompt](./prompt-templates/prd-generation/prd-generation.md) · [Guide](./prompt-templates/prd-generation/README.md) | Rough notes, intended users, and constraints | A draft Product Requirements Document built through questions and confirmation |
| Give your coding assistant clear working rules | [Claude Opus 5 rules](./agent-configs/claude-code-desktop/claude-opus-5/CLAUDE.md) · [Setup guide](./agent-configs/claude-code-desktop/claude-opus-5/README.md) | Your existing project instructions and the matching model | Instructions for concise responses, task scope, and tool use |
| Continue a project in a fresh AI chat | [Session-continuation prompt](./prompt-templates/session-continuation/port.md) · [Guide](./prompt-templates/session-continuation/README.md) | The current conversation, while its history is still available | A reviewable handoff with decisions, progress, and remaining tasks |

## Try the PRD prompt

1. Open the [PRD prompt file](./prompt-templates/prd-generation/prd-generation.md) and copy its contents.
2. Replace the text between `BRAINDUMP START` and `BRAINDUMP END` with your idea; fill or remove the other bracketed placeholders.
3. Paste the prompt into your AI chat, answer the questions, and confirm the decisions before asking for the final draft.

Already have a PRD and a concise MVP concept? Use the [ultra-lean build prompt](./prompt-templates/ultra-lean-mvp-development-planning/Guided-Ultra-Lean-MVP.md) to define the first build's purpose, features, and technical approach.

## Choose your next step

You can enter at the step you need; each folder explains its required inputs.

| Step | Resource | Output |
| --- | --- | --- |
| Plan user research | [Research questionnaire](./prompt-templates/user-research-questionnaire/) | Questionnaire draft, then an evidence-linked PRD input from collected responses |
| Define the product | [PRD generation](./prompt-templates/prd-generation/) | Goals, users, requirements, and constraints |
| Map the experience | [UX and user flow](./prompt-templates/ux-user-flow/) | User journeys and interface requirements |
| Choose the first release | [MVP concept](./prompt-templates/mvp-concept-definition/) | Core problem, hypothesis, and limited feature scope |
| Plan the build | [MVP development plan](./prompt-templates/mvp-development-planning/) or [ultra-lean build specification](./prompt-templates/ultra-lean-mvp-development-planning/) | Detailed development plan or a smaller build specification |
| Plan verification | [Test plan](./prompt-templates/test-plan-generation/) | Test scope, cases, and acceptance criteria |
| Prepare a visual brief | [v0 design prompts](./prompt-templates/v0-design-prompts/) | A design prompt using your UX specification and MVP scope |
| Prepare the next session | [Session continuation](./prompt-templates/session-continuation/) | Current state, corrections, and next tasks |

For the full instructions, see the [prompt template guide](./prompt-templates/README.md).

## Configure your coding assistant

The [agent configuration guide](./agent-configs/README.md) separates behavioral instructions from tool permissions:

* [Claude Opus 5 instructions](./agent-configs/claude-code-desktop/claude-opus-5/README.md): review the model scope and merge relevant rules with your existing project instructions.
* [Claude Code permission guardrails](./agent-configs/claude-code-desktop/permission-guardrails/README.md): an optional strict policy with broad restrictions; read its effects before using it.

The prompts use guided questions, confirmation points, and inputs from earlier steps to help you make explicit decisions. Outputs remain drafts: review requirements, code, and handoffs before relying on them, and remove private information you do not need to share with your AI tool.

**Star this repository to save it for your next project.** If you find an unclear step, [open an issue](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/issues) with the template name and a small, non-sensitive example.

## About and license

I develop these resources using official documentation, AI tools, and my own software development work. My separate [Prompt Rulebook](https://promptquick.ai) covers broader prompting techniques.

This toolkit is free to use, adapt, and share under the [MIT license](./LICENSE).
