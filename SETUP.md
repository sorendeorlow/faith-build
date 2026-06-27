# Faith + Build — Setup (10 minutes)

Two things to do: **(1)** create two Google Forms and paste their links into the site,
**(2)** publish to GitHub Pages.

---

## 1. Create the two Google Forms

Go to <https://forms.google.com> → **Blank form** for each. Copy the questions below
straight in. Set responses to land in a Google Sheet (Responses tab → green Sheets icon).

> Tip: in Form **Settings → Responses**, turn on "Collect email addresses" so you always
> know who replied.

### FORM 1 — "Pull up a chair" (the join / RSVP form)

Keep it short. Suggested questions:

1. **Your name** — Short answer (Required)
2. **Best way to reach you** — Short answer (phone or email) (Required)
3. **Which Wednesday are you thinking of coming?** — Short answer
4. **Any dietary notes for the meal?** — Short answer (so the bread + food works for you)
5. **How did you hear about Faith + Build?** — Short answer
6. **Anything you want me to know?** — Paragraph

### FORM 2 — "Where you are" (the survey + Bible study, two sections)

In Google Forms, click the **= (add section)** button to split this into two sections.

**Section 1 — Where you are right now**

1. **Your name** — Short answer
2. **Where would you put yourself with God right now?** — Multiple choice
   - Just exploring / curious
   - Coming back after time away
   - Steady and growing
   - Leading or pouring into others
   - Honestly not sure — and that's ok
3. **What are you hoping to find in a group like this?** — Checkboxes (allow "Other")
   - Brotherhood / real friendship
   - Accountability
   - Prayer
   - Learning the Bible
   - Building something that serves people
   - A place to bring doubts and questions
4. **What's one thing you're building or wrestling with right now?** — Paragraph
   (a product, a habit, a relationship, a question)
5. **How comfortable are you praying out loud or sharing in a group?** — Linear scale 1–5
   (1 = rather just listen, 5 = love to)
6. **Anything you'd like us to know or pray about?** — Paragraph

**Section 2 — A gentle Bible-study warm-up** (no wrong answers)

7. **What's a figure or story in the Bible you enjoy or connect with? Why?** — Paragraph
8. **Is there a verse that's stuck with you — or one you'd like to?** — Short answer
9. **What's a question about faith or the Bible you'd love to dig into with other men?** — Paragraph
10. **How familiar are you with the Bible?** — Multiple choice
    - New to it
    - I know the highlights
    - I read it fairly often
    - Pretty deep / studied it
11. **What actually helps you take action on what you believe?** — Paragraph
12. **If we built one thing together this season to serve others, what would you love it to be?** — Paragraph

---

## 2. Paste the form links into the site

1. Publish each form: top right **Send → link icon (🔗) → Copy**. (Optionally tick
   "Shorten URL".)
2. Open **`index.html`** and find this block near the top:

   ```js
   window.FORMS = {
     join:   "PASTE_JOIN_FORM_URL_HERE",
     survey: "PASTE_SURVEY_FORM_URL_HERE"
   };
   ```

3. Replace the two placeholders with your real links, e.g.:

   ```js
   window.FORMS = {
     join:   "https://forms.gle/abc123",
     survey: "https://forms.gle/xyz789"
   };
   ```

That's it. Every "Pull up a chair / Sign me up / Save my seat" button opens the join
form; every "Take the survey" button opens the survey. **Until you paste the links, the
buttons fall back to a pre-filled email to soren@resonancepartners.us — so nothing is
ever broken.**

---

## 3. Publish to GitHub Pages

From this folder (`/Users/rpc4/mensgroup`):

```bash
git init
git add .
git commit -m "Faith + Build site"
# create an empty repo on github.com first (e.g. named "faith-build"), then:
git remote add origin https://github.com/<your-username>/faith-build.git
git branch -M main
git push -u origin main
```

Then on GitHub: **repo → Settings → Pages → Build and deployment → Source: Deploy from a
branch → Branch: `main` / `(root)` → Save.**

Your site goes live in ~1 minute at:
`https://<your-username>.github.io/faith-build/`

### Optional: a custom domain (e.g. faithandbuild.com)
- Buy the domain, add a `CNAME` file to this folder containing just the domain.
- In Settings → Pages → Custom domain, enter it and follow the DNS steps.

---

## Editing later
- **Text / sections** → `index.html`
- **Colors, fonts, spacing** → `styles.css` (all colors live in the `:root` block at top)
- After any change: `git add . && git commit -m "update" && git push` — Pages redeploys automatically.
