# Skils3d-animtions

A skill for making 55-70 s vertical animated story shorts: 2D characters in a colourful 3D world, with ink outlines, a painted town, lens blur, gliding cameras, a march score and sound effects. The picture is rendered with three.js inside Remotion on your own computer, with no AI video generator.

It is written to work with **any AI**, not one product: a plain chat AI can plan the short (facts, script, shot plan, sound plan), and an AI that can edit files and run commands can build and render it.

Proven on **The Bridge That Fell for a Song**, a 67 s short about the 1831 Broughton bridge.

## Start here
| You have | Do this |
|---|---|
| A chat AI | Paste [`AI_INSTRUCTIONS.md`](AI_INSTRUCTIONS.md) into its instructions or first message |
| A coding agent on your computer | Open this folder; it reads [`AGENTS.md`](AGENTS.md) |
| Anything else | Read [`docs/USING_WITH_AI.md`](docs/USING_WITH_AI.md) |

## What's inside
| Path | What it is |
|---|---|
| `AI_INSTRUCTIONS.md` | Short instructions any AI can follow (about 5,000 characters) |
| `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md` | Entry points for tools that look for those file names |
| `SKILL.md` | The full pipeline, every rule, every fix, and the final look values |
| `docs/USING_WITH_AI.md` | How to use it in each kind of environment |
| `templates/bridge/` | Full source of the bridge short: world, characters, ink, lens blur, grade, story/camera |
| `templates/audio/` | The synthesized sound: SFX, march music, the mix with ducking and loudness |
| `templates/scripts/` | Stills, side-by-side sheets, shot merge and frame-by-frame QA helpers |
| `references/STYLE_BIBLE.md` | The script and visual formula measured from 20 reference shorts |
| `references/reports/` | Seven measured reports: motion, depth, textures, characters, lighting, outlines, grade |
| `references/frames/` | 38 full-size reference frames (540x960) to compare your frames against |
| `references/sheets/` | 20 contact sheets, one per reference short, 60 frames each (1,200 frames) |

## Notes
- Story, characters and voice should always be your own. Use the references for the look, not the content.
- Set `REMOTION_TMP` to a folder on a big drive. Every Remotion bundle copies about 1.3 GB.

## Credit and license
Based on [`mromidev/claude-animated-shorts`](https://github.com/mromidev/claude-animated-shorts) by mromidev, MIT licensed. The original copyright notice is kept in [`LICENSE`](LICENSE). The universal instructions, entry-point files and docs were added on top. The code and docs are MIT. The reference frames and contact sheets come from other people's videos: they are included for style study only and are not covered by the MIT license.
