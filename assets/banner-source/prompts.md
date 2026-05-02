# Banner source — generation log

Recipe to re-render `../banner.gif` from scratch. Reproducible with the same seed.

## Frame 1 (dim runes — base state)

- **Model:** Z-Image-Turbo (via Hugging Face MCP `gr1_z_image_turbo_generate`)
- **Resolution:** 2016×864 (21:9)
- **Seed:** 7331
- **Steps:** 8
- **Shift:** 3
- **Random seed:** false

Prompt:

> Cinematic ultra-wide banner artwork, dark fantasy meets soft neon synthwave aesthetic, ornate medieval lute and a worn open spellbook resting on a stone pedestal, ancient glowing rune-inscribed monolith standing in the background, soft cyan and amber bioluminescence radiating from the runes, drifting embers and floating motes of light, low swirling mist along the stone floor, deep teal and obsidian color palette with warm gold accents, painterly brushwork, atmospheric depth, candlelight glow, mystical bardcore mood, wide negative space in the center for a text overlay, no people, no characters, no text, no letters, professional concept art, highly detailed, 8k

Output: `frame-01.webp` → composited with text → `frame-01-titled.png`

## Frame 2 (bright runes — pulse peak)

Same model / resolution / seed / steps / shift as Frame 1. Only the prompt changes — same scene, brighter rune state.

Prompt:

> Cinematic ultra-wide banner artwork, dark fantasy meets soft neon synthwave aesthetic, ornate medieval lute and a worn open spellbook resting on a stone pedestal, ancient glowing rune-inscribed monolith standing in the background pulsing with intense bright cyan and golden bioluminescence, runes burning brighter than before, more visible drifting embers and floating motes of golden light, glowing wisps of mist swirling along the stone floor, deep teal and obsidian color palette with warm gold accents, painterly brushwork, atmospheric depth, candlelight glow stronger, mystical bardcore mood, wide negative space in the center for a text overlay, no people, no characters, no text, no letters, professional concept art, highly detailed, 8k

Output: `frame-02.webp` → composited with text → `frame-02-titled.png`

## Wordmark overlay

Rendered with ImageMagick.

```bash
convert -background none \
  -font /usr/share/fonts/truetype/dejavu/DejaVuSerif-Bold.ttf \
  -fill "#f7d986" -stroke "#0d0805" -strokewidth 2 \
  -pointsize 110 -kerning 10 \
  label:"THE BARD CHAT" \
  \( +clone -background "#ff9a3c" -shadow 90x18+0+0 \) +swap \
  -background none -layers merge +repage \
  text-layer.png
```

Composite onto each frame (centered, nudged 40px above center to land in the densest negative space):

```bash
composite -gravity center -geometry +0-40 text-layer.png frame-01.webp frame-01-titled.png
composite -gravity center -geometry +0-40 text-layer.png frame-02.webp frame-02-titled.png
```

## Crossfade GIF

```bash
ffmpeg -y -hide_banner -loglevel warning \
  -loop 1 -t 1.5 -i frame-01-titled.png \
  -loop 1 -t 1.5 -i frame-02-titled.png \
  -filter_complex "
    [0:v]scale=960:412,setpts=PTS-STARTPTS,split=2[a1][a2];
    [1:v]scale=960:412,setpts=PTS-STARTPTS,split=2[b1][b2];
    [a1][b1]xfade=transition=fade:duration=1.2:offset=0.3[ab];
    [b2][a2]xfade=transition=fade:duration=1.2:offset=0.3[ba];
    [ab][ba]concat=n=2:v=1:a=0,fps=10,split=2[s0][s1];
    [s0]palettegen=stats_mode=full:max_colors=96[p];
    [s1][p]paletteuse=dither=bayer:bayer_scale=5" \
  -loop 0 banner-draft.gif
```

- Final size: 960×412 (matches 21:9 → renders well at any GitHub README width)
- Duration: 3 seconds (1.5s A→B, 1.5s B→A), seamless loop
- File size target: ≤2 MB
- Achieved: 1.9 MB

## To re-render

If the brand essence shifts and you want a different scene:

1. Edit prompts above (keep "wide negative space in the center" instruction so the wordmark still fits)
2. Re-run both Z-Image-Turbo generations with the same seed (or pick a new one and update this file)
3. Re-run the ImageMagick + ffmpeg pipeline above
4. Replace `../banner.gif`
