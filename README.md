# GraveCareUkraine.com

Static website — deployed via Netlify, content managed via `site.json`.

## File structure

```
public/
  index.html      ← the live website
  success.html    ← shown after order form submitted
content/
  site.json       ← ALL editable content lives here
```

---

## How to update content

1. Open this file in GitHub browser:
   `https://github.com/GCUkraine/GraveCareUkraine.com/edit/main/content/site.json`
2. Edit any value (price, text, contact, testimonial...)
3. Click **Commit changes → Commit directly to main**
4. Netlify redeploys automatically in ~45 seconds

> **Bookmark that URL.** It's your CMS for now.

---

## What you can edit in site.json

| Field | What it controls |
|---|---|
| `email` | Contact email (form + footer) |
| `telegram` | Telegram username (all buttons) |
| `whatsapp` | WhatsApp number with country code |
| `heroHeadline` | Main headline on homepage |
| `heroSubtext` | Subtext below headline |
| `totalServices` | Stat shown in hero (e.g. "1000+") |
| `since` | Years of experience stat |
| `citiesCount` | Cities covered stat |
| `guarantee` | Guarantee text in order section |
| `services[]` | All service cards — name, price, description, includes |
| `testimonials[]` | Customer reviews |
| `cities[]` | City tags shown on site |

---

## One-time setup

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/GCUkraine/GraveCareUkraine.com.git
git push -u origin main
```

### 2. Connect Netlify
- netlify.com → Add new site → Import from Git → GitHub
- Select `GCUkraine/GraveCareUkraine.com`
- Build command: *(leave empty)*
- Publish directory: `public`
- Deploy site

### 3. Add your real contacts
Edit `content/site.json` and set your real `email`, `telegram`, `whatsapp`.
Also update same values in `public/success.html` (lines 23–24).

### 4. Connect domain
Netlify → Site configuration → Domain management → Add `gravecareuakraine.com`
Add DNS records at your registrar as Netlify instructs.

### 5. Enable form notifications
Submit a test order → Netlify dashboard → Forms → order-request → Form notifications → add your email.

---

## Coming next (don't touch yet)
- `scripts/` — Google Sheets sync (Option 1, coming soon)
- `scripts/` — Notion sync (Option 2, coming later)
- `.github/workflows/` — automated triggers

---

*Built with Claude · Deployed on Netlify · Free tier*
