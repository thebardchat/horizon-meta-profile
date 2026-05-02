# Meta Avatars Store — wearables submission

The path for getting branded `thebardchat` items onto the actual Meta Avatar (the one shown on your Horizon profile, in Messenger, in Quest social spaces). You can't replace the whole avatar with a custom 3D model, but you **can** ship custom **wearables** (outfits, accessories) that any Meta user can wear — and you'll wear them yourself.

> **Important:** This program's exact rules and entry points have shifted multiple times. Treat this doc as the playbook framework; verify current specifics on the Meta developer portal before submitting. Links and step names may have changed by the time you read this.

## What you can submit

Roughly, the categories Meta accepts for avatar wearables:

- **Tops** — shirts, jackets, robes, cloaks
- **Bottoms** — pants, skirts, leggings
- **Outfits** — top + bottom as a single set
- **Footwear** — boots, shoes
- **Headwear** — hats, hoods, helmets
- **Hair** (sometimes restricted to approved partners)
- **Accessories** — necklaces, bags, instruments-as-accessories
- **Eyewear** / **Facial hair** — limited

For The Bard Chat specifically, the highest-leverage submissions are probably:

1. **A hooded bardic cloak** in deep teal + gold (lifted directly from the avatar concept art) — top category
2. **A glowing-rune lute slung across the back** — accessory category (verify Meta accepts musical instruments as accessories; sometimes they're in a "back item" subcategory)
3. **A worn spellbook satchel** — bag accessory

Each submission is one item. If you submit a "bardic outfit," that's one slot. If you want the cloak available separately for users who already have pants, submit it as a top.

## File format & rigging requirements (what Meta typically expects)

Specifics drift, but the through-line for years has been:

- **Mesh format:** FBX (most common) or glTF
- **Skeleton:** must conform to the **Meta Avatar skeleton** — Meta provides a reference rig and weights through their Avatars SDK. You **cannot** ship a custom skeleton; your wearable rides on top of Meta's.
- **Polycount:** strict caps (varies by category — accessories ≪ outfits). Meta publishes per-slot polycount limits in their submission docs.
- **Textures:** PBR — albedo / base color, normal, metallic-roughness, optionally emissive. Texture resolutions also capped per slot (typically 1024×1024 or 2048×2048).
- **LODs:** at least 2 levels of detail required (LOD0 = full, LOD1+ = simplified) so the wearable performs at distance and on lower-end Quest hardware.
- **No animations on the wearable itself** — animations come from the underlying Meta Avatar skeleton. Wearables move *with* the avatar, not on their own. (Glow / emissive effects are allowed via materials.)

## The submission flow (high-level)

1. **Apply to be a creator** on Meta's developer / horizon-creators portal
   - Likely entry point: https://developers.meta.com/horizon/ (or whatever it's redirected to by now)
   - Possibly also: https://horizon.meta.com/creators/
   - You may need to verify a payment / payout method (this is a paid program; Meta takes a cut, you get rev share)

2. **Download the Avatars Wearables SDK / sample package**
   - Meta ships a Maya / Blender / Unity sample with the official skeleton, sample garments, and the FBX export rig
   - You build your wearable inside that template

3. **Build the wearable**
   - Model in Blender / Maya / your DCC of choice
   - Skin to the Meta Avatar skeleton using the provided weights as a starting point
   - Bake textures
   - Export FBX with embedded textures or as a package per Meta's submission spec

4. **Submit through the creator portal**
   - Upload the FBX + textures + thumbnail
   - Fill in metadata: name, description, price tier, category, tags
   - Wait for review (historically: 2–6 weeks)
   - Meta may reject for: poor topology, broken weights, IP/style violations, performance failures
   - Iterate and resubmit as needed

5. **Once live**
   - Item appears in the Meta Avatars Store
   - Any Meta user can buy and wear it
   - You get a revenue share per sale (terms in the creator agreement; historically ~25–30% to creator after platform fees)

## Cost / time / risk realities

- **Time:** From "I want to do this" to "first item live in the store" is realistically **2–4 months** for a first-time submitter — most of it is rigging, polish, and review iterations
- **Cost:** No fee to apply, but you need 3D production capacity (Blender is free; an artist costs money if you outsource)
- **Risk:** Rejections are common on first submission. Style guidelines are strict. Meta won't approve anything that looks like another brand's IP.
- **Reward:** Real branding moat. The Bard Chat cloak that Meta users buy = walking advertisement across the entire Meta avatar surface.

## Practical "how to actually start" path

1. **This week:** confirm the program is open and bookmark the current submission docs
   - Visit https://developers.meta.com/horizon and search "avatars" / "wearables"
   - If gated, apply to creator program and wait for approval
2. **Within 2 weeks:** download the Avatars SDK + sample template
3. **Within 1 month:** prototype one wearable (recommend the bardic cloak — highest visual impact, simplest topology)
4. **Within 2 months:** submit, iterate on rejections
5. **Once shipped:** add it to the Horizon profile copy, mention it in `promotion/share-kit.md`, and the brand officially has a wearable footprint

## Files to track in this repo (when you start)

If/when you build wearables, scaffold a sibling folder structure:

```
wearables/
├── bardic-cloak/
│   ├── source/         # .blend / .ma source files
│   ├── exports/        # FBX + textures ready for submission
│   ├── thumbnails/     # store listing imagery
│   └── submission.md   # notes on what was submitted, when, status
├── rune-lute/
│   └── ...
└── README.md           # which items exist, which are submitted, which are live
```

Don't create that scaffold until you actually have a wearable in progress — empty folders are noise.

## Honest expectation-setting

This is a **brand investment**, not a quick-win. If the goal is "have a cool avatar tomorrow," skip this and use the parts editor at meta.com/avatars with the concept art as reference. If the goal is "ship branded items that any Meta user can wear and that compound brand value over years," this is the path.

Most creators don't ship wearables. The ones who do tend to be musicians, sports brands, film franchises, and dedicated 3D-art creators who already have rigging muscle. Pick the path that matches your bandwidth.
