# Privacy checklist — creator-account defaults

Recommended settings for a **public creator** account. Walk through these in the Meta Quest mobile app and the Meta Horizon mobile app. Settings are grouped by where they live in the UI; menu paths may shift slightly between app versions.

> **Posture:** "Public by default, friction at the DM layer." Anyone can find/follow the profile, but unsolicited DMs and in-world invites have guardrails.

## Account privacy (Meta Quest app → Settings → Account)

| Toggle | Setting | Rationale |
|---|---|---|
| Profile privacy | **Public** | Creator account — discoverability is the point. |
| Followers | **Anyone can follow** | No approval gate. |
| Friend requests | **Anyone can send** | Approve case-by-case. |
| Active status (online indicator) | **Show to friends only** | Keeps strangers from timing your activity. |
| Search by email | **Off** | Avoid leaking the account email through reverse-lookup. |
| Search by phone | **Off** | Same — phone numbers are highly identifying. |

## Personal info visibility

| Field | Visibility | Rationale |
|---|---|---|
| Birthday | **Only me** | Used for age-gating internally, no need to broadcast. |
| Email | **Only me** | Never make this public. |
| Real name | **Only me** *(if Meta separates "real name" from display name)* | Brand persona is `The Bard Chat`, not Shane. |
| Location | **Only me / blank** | Reduces doxxing surface. |
| Pronouns | **Public** if set | Harmless if set, doesn't matter if not. |

## Messaging (Meta Horizon app → Settings → Messages)

| Toggle | Setting | Rationale |
|---|---|---|
| Who can message you | **Friends and friends of friends** | Most permissive setting that still filters cold spam. |
| Message requests filter | **On** | Cold messages land in a separate folder you can ignore. |
| Read receipts | **Off** | Reduces social pressure to respond. |
| Voice messages | **Friends only** | Friction on cold voice DMs. |

## In-world (Meta Horizon app → Settings → World Activity)

| Toggle | Setting | Rationale |
|---|---|---|
| Who can invite me to worlds | **Friends and friends of friends** | Creators get a lot of "come check this out" invites. Filter the cold ones. |
| Auto-mute strangers | **On** | Default everyone to muted; you can unmute case-by-case. |
| Personal Boundary | **On**, default radius | Standard safety toggle, leave on. |
| Voice mode default | **On**, push-to-talk if available | Push-to-talk is less fatiguing for long sessions. |
| Show me in "Suggested People" | **On** | Discoverability for a creator account. |

## Content + safety (Meta Quest app → Settings → Privacy & Safety)

| Toggle | Setting | Rationale |
|---|---|---|
| Profanity filter | **On** | Default; can disable per-world if context calls for it. |
| Sensitive content filter | **On** | Same. |
| Block list | (manage as needed) | Use generously. Blocking is cheap. |
| Reporting | (read the report flow once so you know it) | Creators need to know how to escalate harassment. |
| Two-factor auth | **On — authenticator app preferred over SMS** | Creator accounts are higher-value targets for takeover. |

## Discoverability (Meta Horizon app → Settings → Discoverability)

| Toggle | Setting | Rationale |
|---|---|---|
| Show me in search | **On** | The whole point of a creator account. |
| Show me in "People you may know" | **On** | Same. |
| Suggest my profile to others | **On** | Same. |
| Allow my profile in Meta search outside Horizon | **On** *(if the toggle exists)* | More inbound traffic. |

## Things to revisit after setup

- After 2 weeks of usage, audit the **Block list** and **Message Requests** folder
- If harassment or spam ramps up, tighten "Who can message you" to **Friends only**
- If you start hosting events, revisit "Who can invite me to worlds" — you may want to open it up for event RSVPs
