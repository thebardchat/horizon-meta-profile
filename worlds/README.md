# Worlds — placeholder for Horizon World builds

This folder is reserved for future **Meta Horizon Worlds** projects authored under `thebardchat`. It's empty today; the structure below is what gets used when the first world is in development.

## Why this matters for the brand

Your **Meta Avatar** (the one on your profile, in social hubs) is locked to Meta's parts library — see `../profile/wearables-submission.md` for the only branding-via-avatar path, which is slow.

Inside a **Horizon World you author**, all of that goes away. You can:

- Use **custom 3D meshes and characters** (glTF / FBX) — including a fully branded "Bard" NPC that visitors meet
- Drop in **custom audio** — original music, voiceover, ambient
- Build **scripted experiences** — interactive storytelling, performances, mini-games
- **Publish to the Worlds catalog** — your world becomes findable in Horizon, separate from your profile

This is where The Bard Chat actually gets to be a *3D character* the way you originally asked about — not as the profile avatar, but as the host inhabiting a world you control.

## When you're ready to start

The recommended on-ramp without a Quest headset:

1. **Meta Horizon Worlds Desktop Editor** (Windows-first, Mac support varies)
   - Authoritative tooling for non-headset world building
   - Requires sign-in with the same Meta account that owns the profile
2. **Horizon Worlds Web Editor** (where supported / when Meta opens access)
   - Browser-based; gated to approved creators in some periods

Both let you import:
- 3D meshes — glTF, FBX
- Textures — PNG, JPG, optionally PBR maps
- Audio — WAV, MP3
- Scripts — TypeScript via Meta's Worlds Scripting API

## Suggested layout (when work begins)

```
worlds/
├── tavern-of-the-bard/        # Working title — first world
│   ├── design/
│   │   ├── brief.md           # What the world is, who it's for, success criteria
│   │   ├── moodboard/         # Reference images, links, inspiration
│   │   └── script.md          # Bard NPC dialogue, story beats
│   ├── assets/
│   │   ├── models/            # .glb / .fbx — bard NPC, props, environment pieces
│   │   ├── textures/          # PBR sets per model
│   │   └── audio/             # Music, voiceover, ambient SFX
│   ├── scripts/               # TypeScript — interactive logic
│   ├── thumbnails/            # Cover art for the Worlds catalog listing
│   └── submission.md          # Publish history, version notes, store listing copy
└── README.md                  # this file
```

## First-world recommendation

**The Tavern of the Bard** — a small, atmospheric tavern interior with:

- A persistent NPC bard (custom mesh, modeled after the avatar concept art in `../assets/avatar-refs/`) that greets visitors and offers a short interactive story chosen from a menu
- Original or royalty-free instrumental music looping in the background
- Glowing rune props matching the banner aesthetic
- A "leave a name in the guestbook" interaction that shows recent visitors

Tight scope, high atmosphere, perfectly on-brand. Ships in days-to-weeks rather than months.

## Out of scope for this folder (right now)

- Anything pre-empting world build — keep design docs / scripts / models OUT of the repo until there's a world being actively built
- Audio assets that aren't licensed for redistribution — track those externally, reference by source not by file
- Rendered / playable builds — these go to the Worlds catalog, not git

## Cross-links

- Avatar concepts that the in-world NPC should resemble: `../assets/avatar-refs/`
- Brand visual language for the world's set dressing: `../assets/banner-source/prompts.md`
- Constitution (operating doctrine): https://github.com/thebardchat/constitution
