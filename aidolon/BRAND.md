# Aidolon — Brand sheet (v0 draft)

> Single source of truth for the Aidolon RCS sender registration on Twilio.
> All values here also feed downstream brand surfaces (App Store listing, website, etc.).
> **DRAFT — review before submitting to Twilio.**

## Identity

| Field | Value |
|---|---|
| **Display name** | Aidolon |
| **Tagline** | Your AI eidolon. |
| **Description (short, ≤100 chars)** | A voice-first AI companion for Ray-Ban Meta glasses. |
| **Description (long)** | Aidolon is a voice-first AI companion for Ray-Ban Meta glasses. Wake it with a word, talk to it like a person, and it sees what you see, sends messages, manages your day, and answers questions in real time. |
| **Brand owner** | Slothful |
| **Pronunciation** | *eye-doh-lon* |
| **Etymology** | Greek *eidolon* (εἴδωλον — phantom, idealized image), respelled to surface the "AI" pun. |

## Visual

| Field | Value |
|---|---|
| **Accent color** | `#4A3FB8` (deep indigo) |
| **Contrast vs white** | ~8.97 : 1 (passes WCAG AAA, exceeds Twilio's 4.5 : 1 minimum) |
| **Logo image** | [`logo.png`](./logo.png) — 224×224, PNG, 10 KB |
| **Banner image** | [`banner.jpg`](./banner.jpg) — 1140×448, JPEG q90, 37 KB |

## Contact

| Field | Value |
|---|---|
| **Email** | dexin@slothful.ai |
| **Phone** | *(none provided — Twilio accepts email-only)* |

## Legal URLs

| Field | URL |
|---|---|
| **Privacy policy** | https://dexin-huang.github.io/slothful/aidolon/privacy.html |
| **Terms of service** | https://dexin-huang.github.io/slothful/aidolon/tos.html |
| **Website** | *(none yet — optional)* |

## Asset URLs (for pasting into Twilio Console)

```
Logo:    https://raw.githubusercontent.com/Dexin-Huang/slothful/main/aidolon/logo.png
Banner:  https://raw.githubusercontent.com/Dexin-Huang/slothful/main/aidolon/banner.jpg
Privacy: https://dexin-huang.github.io/slothful/aidolon/privacy.html
ToS:     https://dexin-huang.github.io/slothful/aidolon/tos.html
```

## How these assets were generated

Logo and banner were generated locally with `D:\Projects\img-cli` (Gemini 3.1 flash image preview), then resized/optimized with Pillow. Recipes:

**Logo** (224×224 PNG, 10 KB)
```bash
node D:/Projects/img-cli/img.js generate \
  "minimalist circular logo for Aidolon, an AI eidolon — voice-first AI companion. A deep indigo crescent halo enclosing a single luminous silver point of light at center, suggestive of both a watching eye and a glowing aperture. Ethereal, phantom-like, premium technology brand mark. Symmetrical, balanced." \
  --style logo -o aidolon/_raw_logo.png
# then crop-square + Lanczos resize to 224x224, PNG optimize
```

**Banner** (1140×448 JPEG q90, 37 KB)
```bash
node D:/Projects/img-cli/img.js generate \
  "wide cinematic hero banner for Aidolon, a voice-first AI eidolon companion for smart glasses. Composition: a luminous deep indigo crescent halo enclosing a single softly glowing silver pearl, positioned on the left third of the frame. Background: deep midnight indigo gradient fading to rich black on the right, with a subtle drifting particle haze suggesting AI consciousness and ethereal presence. Premium, ethereal, modern, minimal. No text, no UI elements, no people. Cinematic lighting." \
  --ratio 21:9 --size 2K -o aidolon/_raw_banner.png
# then center-crop to 2.5446:1 + Lanczos resize to 1140x448, JPEG q90
```

To re-render: re-run the commands above and rerun the resize logic (or recreate `_resize.py` from git history).
