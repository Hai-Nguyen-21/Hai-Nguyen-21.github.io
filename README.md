# Nguyen Le Hai — Portfolio

Personal portfolio website of **Nguyen Le Hai**, Business Analyst.

## 🌐 Live Website

> **[hainguyen-hyper.github.io](https://hainguyen-hyper.github.io)** *(update this after deploy)*

## 📁 Project Structure

```
porfolio/
├── index.html          ← Main file (all-in-one: HTML + CSS + JS)
├── public/
│   ├── avatar.png      ← Profile photo
│   ├── favicon.svg     ← Favicon
│   └── icons.svg       ← Icon sprite
├── assets/
│   ├── fonts/          ← Local fonts (if any)
│   ├── icons/          ← Icon files
│   └── images/         ← Additional images
├── .gitignore
└── README.md
```

## 🚀 Deploy to GitHub Pages

### First time

```bash
# 1. Create a repo named: <your-github-username>.github.io
# 2. Push this folder to it
git init
git add .
git commit -m "Initial portfolio"
git remote add origin https://github.com/<username>/<username>.github.io.git
git push -u origin main
```

### GitHub Pages Settings

1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `(root)`
4. Save → site will be live at `https://<username>.github.io`

### Update content

Just edit `index.html` and push:

```bash
git add index.html
git commit -m "Update portfolio content"
git push
```

## ✨ Features

- 🌗 Dark premium design (black + cream/gold palette)
- 🌐 Bilingual: English / Vietnamese (toggle in top-right)
- 📱 Fully responsive
- 🎭 Smooth animations & scroll reveal
- 🪟 Project case study modal
- ⚡ Zero dependencies — pure HTML, CSS, JavaScript
- 🔍 SEO ready (meta tags, semantic HTML)
