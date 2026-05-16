# Haonan Wang — Personal Academic Page

Single-file static site (HTML + embedded CSS), designed for GitHub Pages.
Modern al-folio-inspired layout with NUS orange accent.

## File structure

```
.
├── index.html        # The whole site (HTML + CSS in one file)
├── assets/
│   ├── avatar.jpg    # Profile photo
│   └── cv.pdf        # (Add your CV here — currently a placeholder link)
└── README.md
```

## Deploy to GitHub Pages (5 minutes)

### 1. Create the repo

On GitHub, create a **new public repo** with this exact name:

```
haonan3.github.io
```

> The repo name must match `<your-username>.github.io`. This makes it a "user site"
> and GitHub auto-publishes it at `https://haonan3.github.io`.

### 2. Push these files

Open a terminal in this folder and run:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/haonan3/haonan3.github.io.git
git push -u origin main
```

### 3. Enable Pages

1. Go to your repo on GitHub → **Settings** → **Pages**
2. Under **Source**, select branch `main` and folder `/ (root)`
3. Click **Save**
4. Wait ~1 min, then visit https://haonan3.github.io

### 4. Updating the site

Just edit `index.html`, then:

```bash
git add . && git commit -m "Update content" && git push
```

GitHub Pages auto-redeploys in ~30 seconds.

## How to edit common things

All edits happen in `index.html`. Search for these landmarks:

| What you want to change      | Where to look                     |
|------------------------------|------------------------------------|
| Name / tagline / bio         | `<!-- HERO -->` section            |
| Email / social links         | `<div class="socials">` block      |
| Research interests           | `<!-- ABOUT / RESEARCH INTERESTS -->` — duplicate `<div class="interest">` |
| News items                   | `<!-- NEWS -->` — duplicate `<li class="news-item">` |
| Add a publication            | `<!-- PUBLICATIONS -->` — copy an existing `<article class="pub">` |
| Experience entry             | `<!-- EXPERIENCE -->` — copy an existing `<li class="exp-item">` |
| Theme color                  | Top of `<style>`, change `--accent` |
| Fonts                        | Top of `<style>`, change `--serif` and `--sans` |

## Replacing the avatar / CV

- Replace `assets/avatar.jpg` with your photo (square, ≥400×400 recommended).
- Drop your CV at `assets/cv.pdf`. The CV button already links there.

## Local preview

Just open `index.html` in any browser. No build step.

For a slightly nicer dev experience (auto-reload, etc.):

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Optional: custom domain

If you want to use e.g. `haonanwang.me`:

1. Buy the domain from any registrar.
2. In your registrar's DNS panel, add these records:
   - `A` record `@` → `185.199.108.153` (and `.109/.110/.111`)
   - `CNAME` record `www` → `haonan3.github.io`
3. In your repo, create a file named `CNAME` containing one line: `haonanwang.me`
4. In repo Settings → Pages, set Custom domain to your domain and enable HTTPS.

---

Built with ● in Singapore.
