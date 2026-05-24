# Flowstate — Deploy to GitHub Pages

Your Flowstate app is ready to go live at `https://<your-username>.github.io/flowstate/` (or a custom domain).

## 🚀 Deploy in 4 Steps

### 1. Create a new GitHub repo

Go to [github.com/new](https://github.com/new) and:
- **Name:** `flowstate` (or any name you like)
- **Visibility:** Public (required for free GitHub Pages)
- **Don't** initialize with README — you'll push your existing code

### 2. Push your code

Open a terminal in your project folder and run:

```bash
git init
git add .
git commit -m "Initial commit — Flowstate"
git branch -M main
git remote add origin https://github.com/<YOUR-USERNAME>/flowstate.git
git push -u origin main
```

Replace `<YOUR-USERNAME>` with your GitHub username.

### 3. Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Build and deployment**:
   - Source: **GitHub Actions** ✅
4. That's it. The workflow file I added will handle the rest.

### 4. Wait ~1 minute

Your app will be live at:

```
https://<YOUR-USERNAME>.github.io/flowstate/
```

(Use your repo name instead of `flowstate` if you picked a different one.)

---

## 🔄 Auto-Deploy on Push

The workflow I added (`.github/workflows/deploy.yml`) will:
- Run automatically every time you push to `main`
- Build your project fresh
- Deploy to GitHub Pages

So your normal workflow becomes:
```bash
git add .
git commit -m "update"
git push
# → site updates in ~1 minute
```

---

## 🎯 Using a Custom Domain (optional)

1. In **Settings → Pages**, add your custom domain (e.g. `flowstate.app`)
2. Create a file at `public/CNAME` with just the domain on one line
3. At your DNS provider, add a CNAME record pointing to `<your-username>.github.io`

---

## 🛠️ Local Development

```bash
npm install    # first time only
npm run dev    # start dev server
npm run build  # production build to dist/
npm run preview # preview production build
```

---

## 📦 What Gets Deployed

- The `dist/index.html` file (~270 KB) — a **self-contained** app
- No backend, no database, no server
- All state saved to localStorage in the user's browser
- Works offline once loaded

---

## ❓ Troubleshooting

**Page is blank after deploy?**
Wait 60 seconds. Check the **Actions** tab on your repo for build logs.

**Want to use the root URL (username.github.io)?**
Name your repo `<your-username>.github.io` exactly. Then it deploys at `https://<your-username>.github.io/` with no subpath.

**404 on refresh?**
Not an issue — Flowstate is a single HTML file with no routing, so there are no subpages to worry about.
