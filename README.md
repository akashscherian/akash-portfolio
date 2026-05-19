# Akash S Cherian — Personal site

Static personal site / portfolio. Built as plain HTML + CSS + a tiny bit of JS — no build step, no framework.

## Structure

```
.
├── index.html                  Landing page
├── projects/
│   ├── wazuh-soc.html         Wazuh SIEM home lab write-up
│   ├── iso27001.html          ISO 27001 risk-assessment write-up
│   └── agribot.html           IEEE Agri-Bot project page
├── assets/
│   ├── styles.css             Shared stylesheet
│   └── main.js                Tiny JS (sets year in footer)
├── resume.pdf                 Your résumé (REPLACE THIS — see below)
├── vercel.json                Vercel config (clean URLs, security headers)
└── README.md
```

## Before you deploy

1. **Drop your résumé in.** Put your latest résumé at the project root and name it `resume.pdf`. The "Download résumé" buttons on the site link to `/resume.pdf`. If you'd rather link to the .docx, change the `href="resume.pdf"` references in `index.html` to point at your file (e.g. `resume.docx`).
2. **Sanity-check the content.** Look through every page once — make sure the dates, names, and project descriptions match how you talk about them in interviews.
3. **(Optional) Custom domain.** Vercel gives you a `*.vercel.app` URL for free. You can add a custom domain later under Project Settings → Domains.

## Deploy to Vercel — two options

### Option A: drag-and-drop (fastest, ~2 minutes)

1. Zip this entire folder.
2. Go to <https://vercel.com/new>.
3. If asked, sign in (GitHub login is easiest).
4. Choose "Deploy" → drag the zip onto the upload area (or use the "Browse" button to select it).
5. Vercel detects it as a static site automatically. Click **Deploy**.
6. Done — you'll get a URL like `akash-s-cherian.vercel.app`.

### Option B: GitHub + Vercel (best for updates later)

1. Create a new repo on GitHub (public or private). Name it something like `akash-portfolio`.
2. From this folder in your terminal:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/akash-portfolio.git
   git push -u origin main
   ```
3. Go to <https://vercel.com/new>, click **Import Git Repository**, pick the repo you just pushed.
4. Leave all defaults (Framework Preset: **Other**, Build Command: empty, Output Directory: empty).
5. Click **Deploy**.

Every future `git push` to `main` will redeploy automatically.

## Editing later

The site is plain HTML — open any file in a text editor and change the text. To preview locally without a server, just double-click `index.html`. To run a proper local server (so relative paths work the same as on Vercel):

```bash
# Python 3
python3 -m http.server 8000
# then open http://localhost:8000
```

## Add a new project write-up

1. Copy `projects/wazuh-soc.html` to `projects/your-new-project.html`.
2. Replace the content inside `<section class="project-hero">` and the project-body section below it.
3. In `index.html`, copy one of the project cards and update the title, description, tags, and the `href` to point at your new page.

That's it. No build step, no rebuild needed.

## License / credit

Site content (text, project write-ups) © Akash S Cherian. Feel free to reuse the structure and CSS for your own portfolio.
