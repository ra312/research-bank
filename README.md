# Research Ideas

ML research hypotheses, validation plans, and results — published at
**https://ra312.github.io/research-bank/**

---

## One-time GitHub Setup (Phase 1)

### 1. Create the repository

```bash
# From this folder
git init
git add .
git commit -m "Phase 1: Jekyll base site with MathJax"
```

Go to https://github.com/new and create a **public** repository named exactly:
```
research-bank
```
Do **not** initialise with a README (you already have one).

```bash
git remote add origin git@github.com:ra312/research-bank.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repo → **Settings → Pages**
2. Under **Build and deployment**, set **Source** to **GitHub Actions**
3. Save.

The first workflow run starts automatically when you push. After ~2 minutes
the site is live at `https://ra312.github.io/research-ideas/`.

### 3. Verify Phase 1

Open `https://ra312.github.io/research-ideas/` — you should see the homepage
with two test equations rendered as math (not raw LaTeX).

---

## Writing Research Ideas (Phase 2+)

Add `.tex` files to `_tex/` following `_tex/TEMPLATE.tex`.
Push to `main` and the CI pipeline compiles them to posts automatically.

## Browser Editing (Phase 3+)

Visit `https://ra312.github.io/research-bank/admin/` and log in with GitHub.
