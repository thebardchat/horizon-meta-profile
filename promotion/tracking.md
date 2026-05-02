# Tracking — share params + analytics notes

The share link Meta originally surfaced for this profile is:

```
https://horizon.meta.com/profile/702118972988489/?hwsh=NB71aLyhVb&utm_source=twilight&utm_medium=SHARE&utm_parent=SHARING&utm_cohort=ORGANIC_UNKNOWN
```

That URL has two distinct things tacked onto it.

## `hwsh` — Horizon's share token

`hwsh=NB71aLyhVb` is Meta's internal **horizon-web-share** token. It identifies the share event (which user shared, when, from where in the app). When someone follows the link, Meta can attribute the click back to the share session.

- **Keep `hwsh`** when you want Meta's internal analytics to credit the share
- **Strip `hwsh`** when sharing the "canonical" link in places like a `LICENSE`, a README, an email signature — anywhere you want a stable, non-tracking URL

## `utm_*` — standard UTM params

| Param | Value | Meaning |
|---|---|---|
| `utm_source` | `twilight` | Internal Meta name for the Horizon mobile/web client (one of their codenames) |
| `utm_medium` | `SHARE` | Came from a share action |
| `utm_parent` | `SHARING` | Parent context within Meta's analytics taxonomy |
| `utm_cohort` | `ORGANIC_UNKNOWN` | No paid attribution; cohort unknown at share time |

These are visible to **any analytics tool** that processes the URL (including your own, if you ever route through one). They're not sensitive — they identify the medium, not the user.

## When to use which form

| Use case | Use this URL |
|---|---|
| README, LICENSE, formal docs, email signature | `https://horizon.meta.com/profile/702118972988489/` (clean) |
| Social posts where you want share credit | Full URL with `hwsh` + `utm_*` |
| Personalized friend asks where you want to know who clicked | Generate a **fresh** share link from inside the Meta Horizon mobile app for that specific share — each generated link has a unique `hwsh` |

## Generating fresh share tokens

To get a new `hwsh` for tracking a specific share:

1. Open Meta Horizon mobile app → your profile → **Share** button
2. Each tap of "Copy link" generates a new `hwsh` token
3. Use that link for the specific share you want to track

You don't get a real-time dashboard for these (Meta doesn't expose one to creators yet) — but if Horizon ever ships creator analytics, the data is being captured.

## Don't roll your own UTMs

Don't append your own `utm_*` params on top of Meta's — it confuses Meta's pipeline and isn't readable by you anyway since you don't own the analytics endpoint.

If you want **your own** click tracking (e.g., to know how many people clicked from a specific tweet), use a third-party shortener (Bitly, etc.) that wraps the full Meta URL. Then you get your own click counts independently.
