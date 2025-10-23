# 💡 Vercel Org to Personal Mirror Workflow

**Keep your Vercel preview and production deploys running — even for organization repositories.**

This GitHub Workflow automatically **mirrors your organization repository into a personal account**, so you can connect it to **Vercel** (or any other CI/CD platform) and keep using **free plan deployments** without restrictions.

---

## 🚀 What it does

Every time you `push` to `main` or `develop`:

1️⃣ Clones your organization repo  
2️⃣ Pushes the same branch to a personal repo (the “mirror”)  
3️⃣ Triggers your connected CI/CD (e.g., **Vercel**) automatically

⏱️ 15 seconds of sync + 2–3 minutes of Vercel build → **auto-deploy ready**

---

## ⚙️ Setup guide

1. Create an **empty personal repository** in your GitHub account.  
2. Generate a **Personal Access Token (PAT)** with `repo` permissions.  
3. In your **organization repo**, go to  
   **Settings → Secrets and variables → Actions → New repository secret**  
   Add:
   - `PERSONAL_REPO_PAT` → your token  
   - `PERSONAL_REPO_URL` → e.g. `https://github.com/youruser/repo-mirror.git`
4. Copy [`vercel-org-to-personal-mirror.yml`](.github/workflows/vercel-org-to-personal-mirror.yml)  
   into:
   ```
   .github/workflows/
   ```
5. Push to `main` or `develop` → the mirror syncs automatically 🚀

---

## 🎯 Perfect for

- ✅ Vercel free plan users (preview + production)
- ✅ Organization repos (no direct integration needed)
- ✅ Lightweight CI/CD mirroring

---

## 🔐 Required secrets

| Secret | Description |
|--------|--------------|
| `PERSONAL_REPO_PAT` | Personal Access Token with `repo` scope |
| `PERSONAL_REPO_URL` | HTTPS URL of the personal repository |

---

## 🧠 Why this workflow exists

Vercel doesn’t allow connecting **organization repositories** under free plans.  
This workflow gives you a **clean, automated workaround**: mirror your code to a personal repo, and let Vercel do the rest.

---

## 📜 License

[MIT License](LICENSE) — free to use, modify, and share with attribution.

---

👨‍💻 Created by [@juanisidoro](https://github.com/juanisidoro)  
🔗 Project: **Vercel Org to Personal Mirror Workflow**
