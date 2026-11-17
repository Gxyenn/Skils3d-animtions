# Using this skill with any AI

The instructions in this repo do not depend on one product. What an AI can do depends on the tools it has, not on its name. Find your situation below.

| You have | What to do | What you get |
|---|---|---|
| **A chat AI** (web or app, no files or shell, any provider, including a local model) | Paste `AI_INSTRUCTIONS.md` into its custom / system instructions, or into your first message. If it accepts files, attach the knowledge files listed below. | Facts with sources, script, shot plan, sound plan, hand-off brief. No video. |
| **An AI with a sandbox or terminal in the cloud** | Give it this repo (upload the ZIP or connect it) and ask it to follow `AGENTS.md`. Test it first (see below). | Planning for sure. A full render only if the sandbox passes the test. |
| **A coding agent on your own computer** (CLI or IDE) | Open this folder or your Remotion project, then say: *"Make a short about ... Follow AGENTS.md and stop after the script for my approval."* | The whole pipeline: script, shot plan, stills, render, sound mix, QA. |

Many coding assistants read `AGENTS.md` by themselves. `CLAUDE.md`, `GEMINI.md` and `.github/copilot-instructions.md` are one-line pointers to it, for tools that look for those file names. Tools that support the `SKILL.md` skill format can also use this folder as a skill: name the folder `cartoon-3d-short` and put it in that tool's skills folder (check its docs for the path).

## Knowledge files for a chat AI
Attach as many as it allows, in this order:
1. `SKILL.md`: the pipeline, the rules, the look values
2. `references/STYLE_BIBLE.md`: the script and visual formula
3. `templates/SCRIPT_example.md`: a finished script to copy the beat structure from
4. `templates/bridge/story.ts`: the shot-plan format (rename to `story.ts.txt` if the upload rejects `.ts`)
5. `templates/audio/cues.md`: a finished sound cue sheet

Short on space? `AI_INSTRUCTIONS.md` alone is about 5,000 characters. Some products cap custom instructions (for example, Custom GPTs allow 8,000 characters), so it fits.

## Hand-off from a chat AI to a coding agent
1. Let the chat AI finish steps 1-6 and give you the hand-off brief.
2. Save the approved script as `SCRIPT.md` in your Remotion project.
3. Give the brief to the coding agent and say: *"The script is approved. Continue from step 4 of the pipeline in SKILL.md."*

## Can the cloud sandbox render?
Not verified. Rendering needs Node, Remotion, a Chrome that can do WebGL, and ffmpeg. Ask the AI to run `node -v`, `ffmpeg -version`, `npm i remotion`, then start a headless Chrome. A 2K render ran at about 4 frames per second on a PC with a GPU (about 10 minutes for 67 s), and each Remotion bundle copies about 1.3 GB, so a limited sandbox will be slow or fail. If it fails, render on your own computer.

## Requirements to render
Node, [Remotion](https://www.remotion.dev/) with `@remotion/three`, Python 3 with `numpy`, `scipy` and `Pillow`, ffmpeg, and Chrome. Set `REMOTION_TMP` to a folder on a big drive.

Before the first render:
- Copy `templates/scripts/` into your project's `scripts/` folder and `templates/bridge/` into `src/videos/<name>/`.
- Fix the hard-coded paths (see Gotchas in `SKILL.md`): the Chrome path in `bridge-stills.mjs` and `ROOT` in `bridge_merge.py`.
- The Kenney `.glb` props are not in this repo. The scene renders without them.

## Reference frames
`references/frames/` (38 frames) and `references/sheets/` (20 contact sheets) come from other people's videos. They are for style study and side-by-side checks only: compare your frames against them, but never reuse their characters, shots or scripts. They are large images, so a chat AI does not need them; they matter for the render and review steps.
