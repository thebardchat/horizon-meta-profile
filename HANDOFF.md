# Hand-off — what Shane needs to do next

This repo's documentation work is done locally. The remaining steps require **your account access** (Meta, GitHub) — Claude can't do them. Each step below is short.

## 1. Lock the brand essence (5 minutes)

Pick one direction so we can finish the avatar concept work:

| Direction | Quick description |
|---|---|
| Storytelling AI persona | The Bard is a conversational AI character that tells stories |
| Creator brand for AI tools | Public-facing brand for AI/dev experiments you publish |
| Live VR performer / host | A bard who hosts events, music, talk shows in Horizon |
| Multi-purpose creator umbrella | Catch-all banner for everything you make |

Once locked, ping Claude in this directory and say "brand essence is X" — Claude generates 3–4 avatar concept variations into `assets/avatar-refs/` for you to use as reference at meta.com/avatars.

## 2. Configure the Meta Horizon profile (~30 minutes)

Tools you need:

- A browser signed into your Meta account
- Meta Horizon mobile app
- Meta Quest mobile app

Walk through `profile/setup-walkthrough.md` from top to bottom — it's the click-path. Copy values from `profile/profile-copy.md`. Apply privacy settings from `profile/privacy-checklist.md`.

Verify by visiting [horizon.meta.com/profile/702118972988489](https://horizon.meta.com/profile/702118972988489/) in an **incognito window** — that's what strangers see.

## 3. Build the avatar (~20 minutes, after step 1)

- Once Claude has produced concept refs (after you pick brand essence), open `assets/avatar-refs/` for visual reference
- Open [meta.com/avatars](https://meta.com/avatars) in a browser
- Sign in with the same Meta account
- Use the parts library to assemble something close to the chosen reference (Meta's editor doesn't accept image upload — it's parts-based)
- Save — the avatar propagates to Horizon, Messenger, Instagram (if linked), Quest

## 4. Publish the GitHub repo (~5 minutes)

The repo is ready to push but **needs your authorization** because publishing is irreversible (per your standing scope rule, Claude doesn't push without explicit go-ahead).

When you're ready:

```bash
cd /home/gulfshores/horizon-meta-profile
git init
git add .
git commit -m "Initial commit — Horizon profile setup for thebardchat"
gh repo create thebardchat/horizon-meta-profile --public --source=. --remote=origin --push
```

> Per memory: git operations use this machine's SSH key (already configured for `git@github.com:thebardchat/*`). `gh` uses your stored PAT for the API call to create the repo. Don't embed tokens in the remote URL.

After it's pushed:

- Open https://github.com/thebardchat/horizon-meta-profile in a browser
- Pin it to the `thebardchat` org profile (Org → Pinned → Add)
- Copy the repo URL → paste into the Horizon profile's **Links** field
- Now the loop closes: Horizon profile → repo → constitution → back to Horizon

## 5. Verify end-to-end

- [ ] [horizon.meta.com/profile/702118972988489](https://horizon.meta.com/profile/702118972988489/) (incognito) shows display name, avatar, bio, links
- [ ] github.com/thebardchat/horizon-meta-profile renders with banner GIF animating, README correct, constitution link works
- [ ] From the Horizon profile, the GitHub link → lands on the repo
- [ ] From the repo README, the Horizon link → lands on the profile

## What's already done

- ✅ Repo scaffolded at `/home/gulfshores/horizon-meta-profile/`
- ✅ Animated banner at `assets/banner.gif` (1.9 MB, 960×412, 3-second pulse loop)
- ✅ Banner source frames + ffmpeg recipe at `assets/banner-source/` so you can re-render later
- ✅ Profile copy, setup walkthrough, privacy checklist in `profile/`
- ✅ Promotion kit (share-kit, friend pitch, tracking notes) in `promotion/`
- ✅ Standing rule saved to memory: every `thebardchat/*` repo's README links to https://github.com/thebardchat/constitution

## What's still open

- ⏳ Brand essence not yet locked (blocks avatar concept generation)
- ⏳ Avatar concept refs (`assets/avatar-refs/` is empty, waiting on brand essence)
- ⏳ `assets/social-cards/` (1200×630 share images) — not yet generated; can be done same recipe as the banner once brand is locked
- ⏳ GitHub publication (your authorization)
- ⏳ Meta profile field configuration (your account access)
