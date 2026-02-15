# Put this documentation on Mintlify

Follow these steps to get your NACE Billing docs live on Mintlify.

## 1. Create a new GitHub repository

1. Go to [GitHub](https://github.com/new).
2. Create a **new repository** (e.g. `nace-billing-docs`).
3. Do **not** add a README, .gitignore, or license (you already have content).
4. Copy the repo URL (e.g. `https://github.com/your-org/nace-billing-docs.git`).

## 2. Push this `docs` folder to that repo

From your computer, in a terminal:

```bash
cd /Users/flaminis/Desktop/code/docs

git init
git add .
git commit -m "Initial commit: NACE Billing docs for Mintlify"
git branch -M main
git remote add origin https://github.com/YOUR_ORG/nace-billing-docs.git
git push -u origin main
```

Replace `YOUR_ORG/nace-billing-docs` with your actual GitHub org/username and repo name.

## 3. Connect the repo to Mintlify

1. Go to **[dashboard.mintlify.com](https://dashboard.mintlify.com)** and sign in (use the account you registered).
2. **Create a new doc project** (or open an existing one):
   - If you see “Create documentation” or “Add project”, use that.
   - Otherwise go to **Settings** or **Git settings**.
3. **Connect GitHub:**
   - In **Git settings**, connect the repository you just pushed (`nace-billing-docs`).
   - Set **Branch** to `main` (or the branch you use).
   - Set **Docs path** / **Root directory** to the **root** of the repo (`.` or leave empty), because `docs.json` is at the root of this folder.
4. **Install the Mintlify GitHub App** (if prompted):
   - Go to [dashboard.mintlify.com/settings/organization/github-app](https://dashboard.mintlify.com/settings/organization/github-app).
   - Install the app and grant access to `nace-billing-docs` (or the org that owns it).

## 4. Deploy and get your URL

- After the repo is connected, Mintlify will build and deploy. The site will be at:
  - **`https://<your-subdomain>.mintlify.app`**  
  or the custom domain you set in the dashboard.
- Future pushes to `main` will deploy automatically.

## 5. (Optional) MCP for Cursor/AI tools

Once the site is live, your MCP URL is:

```text
https://<your-subdomain>.mintlify.app/mcp
```

Add this in Cursor (Settings → MCP) so the AI can search this documentation.

---

**Troubleshooting**

- **Build fails:** Check that `docs.json` and all `.mdx` files are in the repo and that the **Docs path** in Mintlify matches the repo root (since `docs.json` is in the root of this folder).
- **Changes not updating:** Confirm the Mintlify GitHub App has access to the repo and that you pushed to the branch selected in Git settings.
- **Need a docs subdirectory:** If you put this folder inside a repo as `docs/`, then in Mintlify set **Docs path** to `docs`.
