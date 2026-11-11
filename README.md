# TranslateES — English ⇄ Spanish Translator Website (GitHub Pages)

A complete static website in the style of a tools + guides hub, built for **GitHub Pages**:

- **Home page** with the translator built in
- **5 working tools:** English→Spanish Translator, Spanish→English Translator, Text to Speech (EN/ES), Word & Character Counter, Spanish Accents & Characters Tool
- **Guides section** with 6 original starter articles (editable from Admin)
- **Pages:** About, Contact, Privacy Policy, Terms, Disclaimer, Editorial Policy
- **Full Admin panel** (`admin.html`): site settings, **Header Code** insert, **article publish/edit/delete**, tools on/off + rename, **admin email & password change**, GitHub publishing

The translator uses the free **MyMemory** translation API (no key needed). A small built-in dictionary covers common words if the API's free daily limit is reached.

---

## 1) Put it on GitHub Pages

1. Create a new GitHub repository (e.g. `translatees`). For a root site name it `YOUR-USERNAME.github.io`.
2. Upload **all files and folders from this package** to the repository (keep the folder structure: `assets/`, `data/`).
3. In the repo: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`** → Save.
4. Your site goes live at `https://YOUR-USERNAME.github.io/translatees/` (or the root URL if the repo is named `YOUR-USERNAME.github.io`).

## 2) Admin login

Open **`https://YOUR-SITE/admin.html`**

- Default email: `admin@site.com`
- Default password: `admin123`

**Change both immediately** in the **Account** tab (current password required).

## 3) Connect GitHub so Admin changes go LIVE

Without this step, Publish buttons only save drafts in your own browser. With it, every Publish commits the change to your repo and GitHub Pages updates the live site in ~1 minute.

1. GitHub → **Settings → Developer settings → Personal access tokens**
   - *Classic token* with the **repo** scope, **or**
   - *Fine-grained token* for this repo with **Contents: Read and write**.
2. In Admin → **GitHub Publish** tab, enter: owner (your username), repo name, branch (`main`), and paste the token.
3. Click **Save & test connection**. Done — Publish buttons are now live.

> The token is stored only in your browser's local storage — it is never written into the site files. Use “Forget token” on shared computers.

## 4) Everyday use

- **Ads / Analytics / verification codes:** Admin → **Header Code** → paste the code → Publish.
- **New article:** Admin → **Articles** → *+ New article* → write (HTML allowed) → Save & publish. It appears on Home + Guides instantly after GitHub Pages refreshes.
- **Tools menu:** Admin → **Tools** → tick/untick, rename, edit descriptions → Publish.
- **Site name & contact email:** Admin → **Site Settings**.
- **Backup:** Admin → **GitHub Publish** → Download `content.json` / `articles.json`.

## Honest security note

GitHub Pages is static hosting — there is no server, so the admin login is a lock screen on the admin page, not server-grade security. The real protection is your **GitHub account + token**: only someone with your token can publish changes to the site files. Keep the token private and your GitHub password strong with 2FA on.

## Files

| Path | Purpose |
|---|---|
| `index.html`, `tools.html`, `guides.html`, `article.html` | Main pages |
| `english-to-spanish-translator.html`, `spanish-to-english-translator.html`, `text-to-speech.html`, `word-counter.html`, `spanish-accents-tool.html` | The 5 tools |
| `about.html`, `contact.html`, `privacy-policy.html`, `terms.html`, `disclaimer.html`, `editorial-policy.html` | Info/legal pages |
| `admin.html` + `assets/admin.js` | Admin panel |
| `assets/site.js` | Loads site settings, injects Header Code, builds header/footer/listings |
| `assets/translate.js` | Translator engine + widgets |
| `assets/style.css` | Design |
| `data/content.json` | Site settings, header/footer code, tools config (edited by Admin) |
| `data/articles.json` | All guides (edited by Admin) |
| `data/admin.json` | Admin email + password hash (edited by Admin) |
