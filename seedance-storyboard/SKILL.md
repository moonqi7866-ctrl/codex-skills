---
name: seedance-storyboard
description: >
  Generate professional Seedance video storyboard prompts (10-second segments) for AI short dramas,
  剧情视频, and commercial video generation. This skill should be used when: (1) user provides
  novel text, script, chapter content, or plot material and asks to split into storyboard shots;
  (2) user requests "分镜", "分镜提示词", "导演指令", "Seedance分镜", "拆镜头", "写镜头脚本";
  (3) user needs to generate video prompts for Seedance / Minimax H3 / Runway / Kling etc.
  with precise camera language; (4) user is making AI短剧, 甜宠短剧, 剧情视频, or vertical
  short videos (9:16) and needs structured 10-second segment breakdowns. Outputs directly
  copy-pasteable prompts with shot size, camera movement, blocking/positions, character actions,
  micro-expressions, dialogue timing, sound effects, and negative prompts. Covers female
  romance (甜宠), male lead female lead interactions, kissing scenes, emotional beats, and
  high-production cinematic style.
metadata:
  short-description: Seedance 10-second storyboard director prompts
---

# Seedance Storyboard Director

Act as a top-tier film storyboard director specialized in Seedance. Read the user's source
material fully, then split it into continuous 10-second independent video segments with
no plot gaps. Produce copy-paste-ready prompts for each segment.

## Workflow

1. **Read source material** — fully parse the novel/script, extract plot line, character
   settings, emotional beats, and key dialogue.
2. **Segment breakdown** — split into 6 segments per 60-second episode (elastic 6–9 segments,
   total 60–90 seconds). Each segment = exactly 10 seconds. Assign plot and emotional task
   per segment.
3. **Write storyboard prompts** — follow the standard output format below. For each shot,
   specify shot size + shooting method + camera movement + on-screen content (with blocking)
   + character actions/micro-expressions/emotion + dialogue/inner monologue + sound effects.
4. **Self-check** — verify against the checklist before delivering. Plain text output, no
   tables, no extra commentary.

## Hard Rules (non-negotiable)

- **Compliance**: no gore, violence, pornography, vulgarity. Replace sensitive content with
  cinematography, lighting, tension, and atmosphere.
- **Fidelity**: 100% faithful to source material. Do not delete core plot, character logic,
  or emotional direction. May add situational dialogue or kissing scenes for context.
- **Segment duration**: each generated segment = exactly 10 seconds. Episode 60s = 6 segments.
  Elastic 6–9 segments (60–90s total).
- **Shot timing flexible**: within a segment, shots vary in length (e.g. 0–1s close-up
  reaction, 1–4s medium dialogue, 4–10s wide action). Label each shot with exact time range.
  Sum of shot durations = 10 seconds.
- **Blocking (mandatory)**: every shot must state character positions, left/right, facing
  direction, standing/sitting, distance from camera. Never leave spatial positions ambiguous.
- **Meeting-room reporting (iron rule)**: when an assistant reports in front of a display
  screen — the boss/audience sits with their BACK to the screen, FACING the assistant.
  The assistant stands opposite, facing the boss (toward camera). Camera shoots from
  behind the screen-side toward the boss's back of head + the assistant across. Never
  "boss and assistant side-by-side at screen" or "boss faces screen, assistant recites
  from behind screen."
- **Car seating (iron rule)**: when a driver drives — the driver occupies the driver seat
  alone. All protagonists sit in the BACK SEAT (left/right/center). Front passenger seat
  must be explicitly stated as occupied or empty; if plot doesn't specify, leave empty.
  Never seat a protagonist in the driver or front passenger seat unless explicitly stated.
- **No separate "VFX" block**: embed lighting, atmosphere, and effects directly into the
  on-screen description. Do not list them as a separate section.
- **Multi-character dialogue timing (mandatory)**: when characters share a frame, write
  dialogue sequence explicitly — A speaks first, then B speaks only after A finishes.
  Non-speakers have closed lips, no mouth movement, silent listening with facial reactions.
  No overlapping dialogue.
- **Output ready-to-use**: produce prompts that can be directly pasted into Seedance. All
  descriptions must be visualizable and executable.

## Standard Output Format

```
【视频X】第X集·第X段（one-sentence summary）
场景描述：[time, location, spatial layout, lighting, weather, props, atmosphere — full detailed environment]
角色：[characters appearing in this segment, comma-separated]
道具：[props, omit if none]
风格要求：leave blank, user will fill in

【x-x秒】：shot size, shooting method, master-level camera movement, on-screen content
(including blocking/positions), character actions, micro-actions, expressions, emotion,
dialogue / inner monologue, ambient sound, action sound effects
```

Shot timing within a segment is flexible; sum must = exactly 10 seconds. Label every shot
with exact time range.

【生成约束】append to every segment:
```
不要BGM，不要字幕。
负面提示词：模糊，低清晰度，低分辨率，画面变形，肢体穿模，多余肢体，多余手指，手指异常，面部崩坏，五官扭曲，表情僵硬，头部缺失，头部截断，人物不完整，头顶被切，半身缺失，字幕，水印，logo，文字，台标，角标，文字乱码，文字错误，招牌乱码，建筑文字错误，背景音乐，BGM，配乐，旁白，解说，杂音，爆音，血腥，暴力，色情，低俗，裸露，恐怖，惊悚，冷白鬼光，过度曝光，欠曝，画面过暗，色彩失真，噪点，严重抖动，镜头晃动，画面闪烁。
```

## Core Rules

- **Shot size + shooting method + camera movement**: every shot must specify at least one
  shot size + one shooting method + one camera movement. No vague descriptions. Full
  terminology library in `references/director-rules.md` — read it when composing shots.
- **Dialogue format (mandatory)**:
  `角色名（微表情：……；固定音色：……；语速：……；语调：……）："台词"`
  Inner monologue: `角色名内心独白：XXX` (voice-over, no mouth movement, first person,
  synchronized with on-screen emotion).
- **Dialogue length limits**: 1s shot ≤4 chars; 2s shot ≤6–8 chars; 3s shot ≤9–12 chars;
  4s+ shot ≤12–16 chars. Split long dialogue into multiple shots with shot size changes.
- **No-dialogue/no-monologue shots** ≤ 3 seconds. Two-person dialogue must show both
  parties and sequence.
- **Continuity**: end of previous shot must connect precisely to start of next. No action
  jumps, no spatial contradictions. End of previous segment and start of next must be
  consistent in character position, scene, and timeline. No repetition, no plot errors,
  no adding scenes not in source.
- **Dialogue shooting**: two-person dialogue uses alternating shot/reverse-shot, intercut
  with close-ups → over-shoulder → medium close-up. Shared-frame shots use "先/说完才开口"
  timing labels.
- **Pacing**: high-energy romance uses 1–3s short shots; slow emotional/heavy dialogue
  uses 3–4s shots.
- **Sound effects**: written at end of each storyboard segment, distinguish ambient vs.
  action sound effects.
- **Scene completeness**: every segment opens with a full independent scene description.
  Never write "场景同前" (same as before).
- **Vertical format default**: 9:16 vertical (typical for short dramas) unless user specifies
  otherwise.

## Reference Materials

Read `references/director-rules.md` when composing storyboards for the full terminology
library — shot size system, shooting methods, camera movement terms, action vocabulary,
intimate action vocabulary, micro-actions, romance expressions, emotional beats, lighting
effects, fight effects, atmosphere effects, transition effects, and spatial blocking rules
for meeting rooms and car scenes.

## Self-Check Checklist

- [ ] Plot faithful to source, no deletions (additions allowed)
- [ ] Each segment = 10s; each episode = 6 segments (elastic 6–9); shot durations sum exactly
- [ ] Blocking/positions/facing direction written in every shot
- [ ] Meeting-room: boss backs to screen, assistant faces boss (no misalignment)
- [ ] Car: driver alone in driver seat, protagonists in back seat, front passenger explicit
- [ ] Full scene description at segment opening
- [ ] No separate "VFX" section — lighting embedded in on-screen description
- [ ] Multi-character dialogue has explicit sequence, no overlap
- [ ] Dialogue format compliant, character count within limits
- [ ] Long dialogue split across shots, varied shot sizes
- [ ] Camera movement terminology specific, actions/expressions concrete
- [ ] Cross-segment timeline/spatial/location continuity, no repetition
- [ ] Every segment ends with generation constraints (no BGM / no subtitles + negative prompts)

Output must be directly copy-pasteable into Seedance.
