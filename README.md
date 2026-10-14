# Jessica Pride, Survivor Lawyer: website

Static site. No build step, no framework, no dependencies.

## Deploy to Vercel

**Drag and drop:** vercel.com/new → deploy this folder → Framework Preset: **Other** → Deploy.

**CLI:**
```
cd website-deploy
npx vercel --prod
```

**GitHub:** push this folder to a repo, import it at vercel.com/new (Framework: Other, no build command, output directory = root). Every push redeploys.

## Pages

| File | Page |
|---|---|
| index.html | Redirects to the homepage |
| Survivor Lawyer Home v2.dc.html | Home (hero video, proof, situations, Jessica, steps, results, heal & learn, attorneys, contact) |
| What Happened.dc.html | 8 situations + California statute of limitations explainer |
| Situation.dc.html | One template for every situation: `?s=schools`, `faith`, `medical`, `travel`, `trafficking`, `workplace`, `prison`, `childhood` |
| Who We Help.dc.html | Survivor groups + loved ones |
| Why Jessica.dc.html | Bio, recognition, results, video, team & Sirona |
| Team.dc.html | Meet the team (expanding portrait panels) |
| Heal and Learn.dc.html | Crisis numbers, self-care videos, YouTube, rights, FAQ, books |
| Articles.dc.html | Article library (search + topic filters) |
| Article.dc.html | One template for every article: `?a=<slug>` |
| Reach Out.dc.html | Private contact form + safe browsing tips |
| Attorneys.dc.html | Attorney referral / co-counsel + referral form |
| Espanol.dc.html | Spanish landing + form + FAQ |
| Site Header.dc.html / Site Footer.dc.html | Shared header and footer, loaded by every page |

## Files

- `support.js` — runtime that renders the `.dc.html` pages. Required; keep it at the root.
- `articles-data.js` — all article content. Add an article by adding an object to `window.ARTICLES`.
- `image-slot.js` — drag-and-drop photo placeholders (Team page).
- `assets/` — photos (p01–p20.jpg), logos, hero video (hero.mp4).

## Before launch: to do

1. **Forms**: Reach Out, Homepage, Español and Attorneys forms show a thank-you state but do not send anywhere yet. Connect each `onSubmit` to the firm's intake/CRM (e.g. Lawmatics, Clio Grow) or a form service.
2. **Team headshots and bios**: Team.dc.html: replace the placeholder roles with real names, titles, quotes, bios and photos.
3. **Articles**: articles-data.js holds 8 sample articles; migrate the real articles and set up 301 redirects from old URLs.
4. **Social links**: confirm Instagram, YouTube, Facebook and LinkedIn URLs in Site Header / Site Footer.
5. **Legal review**: statute-of-limitations copy, results disclaimer, Rule 1.5.1 fee language, Spanish translation.
6. **Analytics**: add GA4 / GTM and call tracking.
7. **Clean URLs (optional)**: rename files to slugs (e.g. `heal-and-learn.html`) and update links, or add `rewrites` in vercel.json.
