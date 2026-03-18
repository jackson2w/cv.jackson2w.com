# Deploying to Cloudflare Pages at cv.jackson2w.com

## Prerequisites
- GitHub account
- Cloudflare account (free tier works)
- `cv.jackson2w.com` DNS managed by Cloudflare

---

## Step 1 — Push to GitHub

```bash
# In the cv.jackson2w.com folder (git is already initialized):
git remote add origin https://github.com/YOUR_USERNAME/cv.jackson2w.com.git
git push -u origin main
```

Create the repo at github.com/new first (name it `cv.jackson2w.com`, set to Public or Private).

---

## Step 2 — Connect to Cloudflare Pages

1. Log into **dash.cloudflare.com**
2. Go to **Workers & Pages → Create application → Pages → Connect to Git**
3. Authorize GitHub and select the `cv.jackson2w.com` repo
4. Configure the build:

| Setting           | Value         |
|-------------------|---------------|
| Project name      | `cv`          |
| Production branch | `main`        |
| Build command     | *(leave empty — static HTML needs no build step)* |
| Build output dir  | `/`           |

5. Click **Save and Deploy**

Cloudflare Pages will deploy automatically on every `git push`.

---

## Step 3 — Add Custom Domain

1. In your Pages project → **Custom domains → Set up a custom domain**
2. Enter `cv.jackson2w.com`
3. Cloudflare will prompt you to add a CNAME record:
   - **Type:** CNAME
   - **Name:** `cv`
   - **Target:** `cv.pages.dev` (your Pages subdomain)
   - **Proxy status:** Proxied (orange cloud ✓)

If your domain DNS is already on Cloudflare, it will offer to add this record automatically.

---

## Step 4 — SSL

SSL is **automatic and free** via Cloudflare. Once the custom domain is verified:
- TLS certificate is provisioned within ~1 minute
- HTTPS enforced automatically
- No configuration required

To force HTTPS: **SSL/TLS → Edge Certificates → Always Use HTTPS → On**

---

## Ongoing Deployment

Any future edits just need:

```bash
git add index.html
git commit -m "Update resume"
git push
```

Cloudflare Pages redeploys in ~20 seconds.
