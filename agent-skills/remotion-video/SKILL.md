---
name: remotion-video
description: Make a short video about a product or brand (promo, launch, explainer, demo or social clip) entirely in code with Remotion, from idea to a rendered MP4 with sound. The owner approves the idea and a storyboard before anything is built.
disable-model-invocation: true
---

<!-- From the AI Product Development Toolkit (https://github.com/TechNomadCode/AI-Product-Development-Toolkit). Paste its skills install line again to update. -->

Make a short video about the owner's product or brand, entirely in code with Remotion: picture, sound and the final MP4. The work follows `brief.md` in this skill's folder. If the file is missing, tell the owner to install the skills again.

The owner answers at two points with "go" or what to change. Build nothing before the first go.

## 1. Proposal, then wait

- If the current folder has a `BRIEF.md`, this is a revision of an earlier video. Read it, propose only the changes the owner asked for, and keep the rest.
- If the owner gave you their own filled brief, use it. Otherwise, fill in `brief.md` yourself.
  - Use what the owner named: a link, a folder or a product.
  - If they named nothing, read the current folder: README, site copy, logo, colours and fonts.
  - If there's nothing to read, ask one question: "What's the video for? Paste a link, a folder path or one sentence."
- Reply with these items, each kept short, in under ten lines in total. Skip intros and extra sections:
  - **Product:** what it is and who it's for, in one sentence.
  - **Kind:** promo, launch, explainer, demo or social clip, taken from the owner's request. If the request doesn't say, use a promo.
  - **Idea:** two or three sentences on how it opens, what happens and how it ends. The story shows what the product does for someone.
  - **Look and sound:** one sentence.
  - **Format:** length, size and frame rate.
  - **New lines:** any on-screen line that isn't from the owner's own material, or "none".
  - **License:** what Remotion's license means for the owner, with the link. Check its official license page first; don't answer from memory.
  - Add one more line only if something blocks the idea, for example missing or low-quality assets.
- End with "Go?". Install nothing and create no files before the answer.

## 2. Storyboard, then wait

- Set up a Remotion project. If the current folder is empty, use it. Otherwise create a new folder next to the product's project. Save the filled brief in it as `BRIEF.md`, so later changes start from it.
- Before writing Remotion code, check its current docs for the installed version.
- Use one timing file for both picture and sound.
- Render 6–8 key frames onto one sheet. Caption each frame with one line about what you see and hear. Send the sheet and end with "Go?".

## 3. Film

- Build the film the brief describes. Make the sound in code: effects and ambience, timed from the same timing file. Use no synthetic voice and no music unless the owner asks for them or provides them.
- Check before delivery:
  - Go through the brief's "Before it's done" list.
  - Step through the frames around every transition. Nothing should pop, jump or vanish between frames.
  - Do a cold read. If you can delegate, have one reviewer who hasn't seen your notes watch a contact sheet as a first-time viewer and say what they understood. Otherwise, do it yourself. Fix whatever confuses them. Run a bigger review only if the owner asks.
  - The MP4 has the expected frame count and resolution. Its audio track is as long as the picture and in sync. Loudness is about -16 LUFS, with true peaks below -1 dBTP.
- Deliver what the brief's "Hand-over" lists, plus what you couldn't check. Always say that nobody has listened to the sound.

## Rules

- Show what the product does for a person. Don't recreate its website or app screens, and don't list features.
- Keep only a few words on screen at a time. Keep the product name and address on screen for at least 2 seconds.
- Every visual must make sense to someone who has never heard of the product. If a metaphor needs explaining, replace it.
- Let the story set the length. Don't rush beats to hit a number.
- When the owner asks for changes, keep everything they didn't mention. Never overwrite an earlier render; save the new one alongside it.
