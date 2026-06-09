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
| `assets/` | Images: `zayvori_logo.png`, `zayvori_icon.png`, `screenshot.png` |

## Brand tokens (styles.css)

| Token | Value | Usage |
|-------|-------|-------|
| `--coral` | `#E2725B` | CTAs, accents, eyebrows |
| `--cream` | `#FAF2E9` | Section backgrounds, hero |
| `--tan` | `#E7C2A6` | Decorative elements |
| `--dark` | `#4A033B` | Text, footer background |

Fonts: `Playfair Display` (headings) and `Inter` (body), loaded from Google Fonts.

## App capabilities (keep website copy aligned with these)

The companion app (`zayvori-app`) is an Expo/React Native recipe app. Accurate feature set:

- **Import recipes** from any URL (food blogs, social media) — paste a link or share directly from another app
- **Smart social parsing** — extracts recipes from Instagram and TikTok captions, handles short URLs and embedded JSON-LD / OpenGraph data
- **Create recipes manually** — title, ingredients, steps, photo
- **My Recipes tab** — all recipes the user has created or saved
- **Collections** — named groups of recipes (e.g. "Weeknight Dinners", "Baking")
- **Search tab** — browse and search recipes shared by other Zayvori users (community discovery)
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

## Deployment

Hosted on GitHub Pages. Push to `main` deploys automatically via the `CNAME` record.
