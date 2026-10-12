# UX and user flow prompt

Step 3 of the [planning prompts](../README.md). The AI turns your PRD into UX and interface specs: the screens, how people move through them, and how each one behaves. Detailed enough for a developer, or an AI design tool, to build from.

**Prompt:** [ux.md](./ux.md)

## What you get

UX specs in seven parts:

1. Information architecture: the screen map, navigation and layout zones
2. Core user flows, including decision points and error paths
3. Screen layouts and their states: empty, loading, filled and error
4. Interaction patterns and feedback
5. Design system notes: components, grid and spacing
6. Accessibility: keyboard paths, screen readers, contrast and focus
7. Technical notes for the frontend

During the interview it sketches layouts in plain text, so you can react to them before anything is written up.

## What to bring

- **Your PRD (required):** the full text, from the [PRD prompt](../2-prd/) or your own.
- **Constraints (optional):** fill in the bracketed line under `TONE & CONSTRAINTS`, such as a design system, devices and browsers, or an accessibility standard, or delete it.

## How to use it

1. Open [ux.md](./ux.md) and copy it with the copy button at the top right of the file (**Copy raw content**).
2. In a text editor, paste your PRD over the placeholder between `--- PRD START ---` and `--- PRD END ---`.
3. Paste it into a new AI chat and answer its questions. It checks its understanding with you before each new section.
4. When it offers to write the specs, say yes. Review them and save them as a Markdown file.

**In Claude Code or Codex?** The `/ux` [skill](../../README.md#skills) runs this same prompt and fills it in from your files.

## Good to know

- Text sketches aren't designs. Try the key screens in a visual prototype before you build them.
- The PRD and the interview make a long conversation, so use a model that keeps it all in view.
- The specs are a draft. Check them against what you know about your users.

## Next step

[MVP scope](../4-mvp-scope/): pick the smallest first version worth building, using your PRD and these specs.

← Previous: [PRD](../2-prd/) · [All planning prompts](../README.md)
