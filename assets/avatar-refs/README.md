# Avatar concept references

Visual references for assembling the Meta Avatar at [meta.com/avatars](https://meta.com/avatars). Meta's editor is parts-based — these don't get uploaded, they're inspiration for what to build.

## Status

- ✅ `01-fantasy-bard.webp` — generated
- ✅ `02-cyber-bard.webp` — generated 2026-05-04
- ✅ `03-minimalist-mark.webp` — generated 2026-05-04
- ✅ `04-mascot.webp` — generated 2026-05-04
- ⛔ `05-turntable-reference.webp` — quota exhausted; re-run with seed 8810, resolution `2016x864 ( 21:9 )`, steps 8, shift 3
- ⛔ `06-fullbody-bard.webp` — quota exhausted; needed for 3D avatar pipeline; re-run with seed 8820, resolution `1024x1536 ( 2:3 )`, steps 8, shift 3

When the quota resets, re-run the blocked prompts below using the Z-Image-Turbo MCP tool with `steps=8`, `shift=3`, `random_seed=false` and the listed seed and resolution.

## 01 — Fantasy bard (rendered)

Classic medieval bard. Hooded teal cloak with gold embroidery, ornate lute, candlelit. Strong narrative hook — reads as "bard" instantly.

- **Seed:** 8801

> Profile avatar portrait, classic fantasy bard, hooded medieval cloak in deep teal and gold, mysterious shadowed face under hood, soft candlelight rim lighting, ornate lute strap visible across chest, dark fantasy painterly style, atmospheric mist, warm golden bioluminescent particles, square 1:1 composition, single subject centered, head and upper shoulders visible, deep teal obsidian background with gold accents, no text, no letters, professional concept art, highly detailed, 8k

## 02 — Cyber-bard / techno-mystic (rendered)

Bard meets neon synthwave. Glowing cyan rune embroidery, holographic lute, electric+gold lighting. Bridges "storyteller" with "AI/VR" — best fit for a creator brand operating in Horizon.

- **Seed:** 8802

> Profile avatar portrait, cyber-bard techno-mystic character, sleek dark hood with glowing cyan circuit-rune embroidery, holographic translucent lute with neon cyan strings, dramatic synthwave rim lighting in cyan and amber, futuristic medieval fusion outfit, mysterious shadowed face partially lit by holographic glow, drifting digital particles, square 1:1 composition, single subject centered, head and upper shoulders visible, deep teal obsidian background with electric cyan and warm gold accents, no text, no letters, professional concept art, highly detailed, 8k

## 03 — Minimalist symbolic mark (rendered)

Abstract logo/sigil rather than a character. Single rune or harp silhouette glowing on a deep field. Cleanest, ages best, doesn't lock the brand to a face.

- **Seed:** 8803

> Minimalist symbolic logo mark, single elegant glowing rune that subtly suggests a stylized harp or lute silhouette, soft cyan and gold bioluminescence, deep teal obsidian background, painterly mystic aesthetic, centered composition, ample negative space around the mark, no text, no letters, no character, no person, professional vector-style concept art, highly detailed, 8k

## 04 — Anthropomorphic mascot (rendered)

A character/creature that IS The Bard. Memorable, brandable, easy to merch.

- **Seed:** 8804

> Profile avatar portrait, anthropomorphic mascot bard character, friendly stylized fox or owl creature wearing a hooded teal cloak with gold embroidery, holding a tiny ornate lute, big expressive eyes, warm candlelit rim lighting, painterly storybook illustration style, atmospheric mist, drifting golden motes, square 1:1 composition, single subject centered, head and upper shoulders visible, deep teal obsidian background with gold accents, no text, no letters, professional concept art, highly detailed, 8k

## 05 — Multi-angle turntable reference (⛔ quota-blocked)

Four views of the chosen bard character (front / three-quarter / side / back) on a single sheet. Useful as visual reference when assembling the parts-based Meta Avatar — Meta's editor doesn't show your reference next to the avatar, so a multi-angle sheet lets you keep the silhouette consistent as you adjust the model.

- **Seed:** 8810
- **Resolution:** `2016x864 ( 21:9 )` (wider than 1:1 to fit the four views)

> Multi-angle character turntable reference sheet, four views of the same fantasy bard character side by side from left to right showing front view, three-quarter view, side view, and back view, hooded medieval cloak in deep teal and gold, ornate lute, mysterious shadowed face under hood, atmospheric mist, warm golden bioluminescent particles, painterly dark fantasy concept art style, neutral grey backdrop for clean reference, no text, no letters, no labels, professional character design sheet, highly detailed, 8k

## 06 — Full-body bard (3D source) (⛔ quota-blocked)

Full-length standing pose, head to toe, on a neutral grey backdrop. Source image for the image-to-3D pipeline (SAM3D-Body / TRELLIS) to produce `assets/avatar.glb`.

- **Seed:** 8820
- **Resolution:** `1024x1536 ( 2:3 )`

> Full body character reference, fantasy bard standing pose, full length head to toe, hooded medieval cloak in deep teal and gold flowing to the floor, ornate lute held in one hand, leather boots, mysterious shadowed face under hood, soft candlelight rim lighting, atmospheric mist around feet, warm golden bioluminescent particles drifting, dark fantasy painterly style, plain neutral grey backdrop, single subject centered with full figure clearly visible from head to feet, no text, no letters, professional concept art, highly detailed, 8k

## After all are generated

Pick one of 01–04 as the primary direction. Use 05 (turntable) plus the chosen primary as combined reference at [meta.com/avatars](https://meta.com/avatars). Meta's editor doesn't accept image uploads — assemble from their parts library to approximate the references.

Once 06 is generated, run the 3D pipeline (SAM3D-Body or TRELLIS) to produce `assets/avatar.glb` for the Pages showcase.
