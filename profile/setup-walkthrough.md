# Setup walkthrough — headset-less profile configuration

You don't need a Meta Quest headset to configure the Horizon profile. You can do nearly everything from web + the two Meta mobile apps. This walkthrough is the recommended order — each step builds on the last.

> **Profile URL:** https://horizon.meta.com/profile/702118972988489/
> **Account email:** the email associated with your Meta account that owns the profile above

## Tools you need

| Tool | Where | What it does |
|---|---|---|
| **horizon.meta.com** | Web (any browser) | View your profile, edit a subset of fields, see who's followed/followed-you |
| **Meta Horizon mobile app** | iOS App Store / Google Play — search "Meta Horizon" | The primary editor for profile fields, friend management, world bookmarks |
| **Meta Quest mobile app** | iOS App Store / Google Play — search "Meta Quest" | Account-level settings (privacy, payment, security), parental, headset pairing |
| **meta.com/avatars** | Web (any browser) | The full-featured Meta Avatar Editor — usable without a headset |

## Order of operations

Do these in order. Each step depends on the prior one being done.

### 1. Sign in on the web

- Go to https://horizon.meta.com
- Sign in with the Meta account that owns the profile
- Visit https://horizon.meta.com/profile/702118972988489/ — confirm you see "Edit profile" or equivalent (proves account ownership)

### 2. Install the two mobile apps

- **Meta Horizon** mobile app — sign in with the same account
- **Meta Quest** mobile app — sign in with the same account
- Some flows route between them; having both installed avoids dead-ends

### 3. Account-level settings (Meta Quest app → Settings)

Set these before profile-level work, since they gate what's visible:

- Account → **Privacy & Safety** → **Profile privacy** = Public *(creator account)*
- Account → **Privacy & Safety** → **Friends** = Anyone can send a friend request
- Account → **Privacy & Safety** → **Active status** = Show to friends
- Account → **Personal info** → **Birthday visibility** = Only me
- Account → **Notifications** → tune to taste; leave creator-engagement notifications on

### 4. Display name + handle (Meta Horizon app → Profile → Edit)

- **Display name:** paste the chosen variant from `profile-copy.md`
- **Username/handle:** `thebardchat` (or fallback)
- Save and confirm it appears on the web profile too

### 5. Avatar (meta.com/avatars on web, OR Meta Quest app → Avatar)

- The web editor at meta.com/avatars is the cleanest experience without a headset
- Use the concept art in `assets/avatar-refs/` as visual reference
- Meta's editor is parts-based: pick face/hair/skin/outfit/accessories. There is **no image upload**.
- Save the avatar — it propagates to Horizon, Messenger, Instagram (if linked), and Quest

### 6. Bio + links (Meta Horizon app → Profile → Edit)

- **Bio:** paste the 150-char variant from `profile-copy.md`
- **Links:** add the 3 links from `profile-copy.md` in the order listed
- Save

### 7. Privacy + discoverability (Meta Horizon app → Settings)

- Walk through `privacy-checklist.md` and apply the recommended setting for each toggle
- Discoverability — confirm "Suggest my profile to others" is **on**

### 8. Verify on the web

- Open https://horizon.meta.com/profile/702118972988489/ in an **incognito** window (so you see what a stranger sees)
- Confirm: display name correct, avatar shown, bio shown, links clickable, no "private" badge
- If anything is missing or hidden, return to the relevant step

### 9. After publishing the GitHub repo

- Add `https://github.com/thebardchat/horizon-meta-profile` to the **Links** field on the profile
- Now the loop closes: Horizon profile → repo → constitution → back to Horizon

## Things that require a headset (deferred)

You cannot do these without a Quest, and they are not needed for profile setup:

- Build a Horizon World in the in-headset world editor (the Web Editor exists but is gated)
- Stream / record from inside Horizon
- Some advanced privacy toggles for in-world voice/visibility
- Spatial profile decoration (banners that show inside Horizon hubs)

When a headset is acquired, revisit and update this walkthrough.
