# Zayvori Web — Claude Code Context

## Project overview

Static marketing and legal website for the Zayvori recipe app. No build step — plain HTML, CSS, and vanilla JS deployed directly.

## File map

| File | Role |
|------|------|
| `index.html` | Main marketing page — hero, features, how-it-works, testimonials, download CTA |
| `privacy.html` | Privacy Policy (UK GDPR + CCPA) |
| `terms.html` | Terms of Service |
| `delete-account.html` | Account deletion instructions (required by app stores) |
| `styles.css` | All styles — BEM-ish classes, CSS custom properties for brand tokens |
| `script.js` | Mobile nav toggle and scroll fade-in animations |
| `CNAME` | Custom domain: `zayvori.com` |
| `auth/callback/index.html` | Deep-link bridge for Supabase email confirmations — redirects `zayvori.com/auth/callback?code=xxx` to the `zayvori://` app scheme; shows a friendly message for `#message=...` responses (email-change old-address step) and a "open on your phone" fallback on desktop |
| `assets/` | Images: `zayvori_logo.png`, `zayvori_icon.png`, `screenshot.png` |

## Brand tokens (styles.css)

| Token | Value | Usage |
|-------|-------|-------|
| `--coral` | `#E2725B` | CTAs, accents, eyebrows |
| `--cream` | `#FAF2E9` | Section backgrounds, hero |
| `--tan` | `#E7C2A6` | Decorative elements |
| `--dark` | `#4A033B` | Text, footer background |

Fonts: `Playfair Display` (headings) and `Inter` (body), loaded from Google Fonts.

## Brand voice & philosophy

Zayvori is a **calm, welcoming alternative to social media** for people who love food. All recipes are public and shared freely — like sitting around one long table where everyone brings something they love.

**Core tone:** Calm, warm, inclusive, simple. Focus on enjoyment, not performance.

**Prefer language like:**
- "save what you like", "discover recipes", "share freely"
- "enjoy cooking", "for yourself and your loved ones"
- "calm", "welcoming", "quiet"

**Avoid language like:**
- "followers", "engagement", "build your audience", "go viral", "top creators"
- any comparison, ranking, or performance language
- "results", "metrics", "grow"

**What Zayvori intentionally does NOT have:**
- Follows or follower counts
- Public profiles or usernames
- Comment sections
- Visible like counts or popularity metrics
- An algorithm ranking content

If a proposed feature or wording contradicts this philosophy, flag it for review rather than implementing it directly.

## App capabilities (keep website copy aligned with these)

The companion app (`zayvori-app`) is an Expo/React Native recipe app. Accurate feature set:

- **Import recipes** from any URL (food blogs, social media) — paste a link or share directly from another app
- **Paste recipe text** — clipboard import mode for copying recipe captions (e.g. TikTok, recipe cards) that can't be shared directly
- **Smart social parsing** — extracts recipes from Instagram and TikTok captions, handles short URLs and embedded JSON-LD / OpenGraph data
- **Create recipes manually** — title, description, serving size, ingredients, steps, photo
- **Serving size** — optional per-recipe serving count (1–10); hidden from viewers when set to 0
- **My Recipes tab** — all recipes the user has created or saved
- **Collections** — named groups of recipes (e.g. "Weeknight Dinners", "Baking")
- **Search tab** — browse and search recipes shared by other Zayvori users (community discovery); imported recipes are private to the importing user and do not appear in Search
- **Like recipes** — heart community recipes; liked recipes appear in a dedicated Liked tab
- **Personal notes** — private per-recipe notes, synced via Supabase
- **Offline support** — failed saves queue locally and sync on reconnect
- **Account settings** — display name, email, password change

Features that do NOT exist (do not add to marketing copy):
- Cook Mode / step-by-step reading mode
- Shared / collaborative collections
- Star ratings
- Meal planning
- Profile photos

## Legal pages — placeholders

`privacy.html` and `terms.html` still contain `[Your Legal Entity Name]`, `[Registered Address]`, and `[Your State]` placeholders. Do not remove these — they need to be filled in by the owner before publishing changes.

## Coming-soon state

The app is not yet publicly available. `index.html` is in "coming soon" mode:
- Hero eyebrow shows "Coming Soon", CTAs say "Notify Me at Launch"
- The download section has a notify-me email capture form instead of store badges
- The download section has a mailto CTA (`hello@zayvori.com`) rather than a form — the site is hosted on GitHub Pages with no backend
- Initial launch is Android only (no Apple Developer account yet); iOS comes later
- When the app launches, revert the eyebrow/CTAs and replace the mailto button with a Google Play badge link; add the App Store badge once iOS is available

## Deployment

Hosted on GitHub Pages. Push to `main` deploys automatically via the `CNAME` record.
