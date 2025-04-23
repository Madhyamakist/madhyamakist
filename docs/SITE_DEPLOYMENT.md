Absolutely — here’s the full SITE_DEPLOYMENT.md file ready for copy-paste:

# 🌐 Madhyamakist Website Deployment Guide

This guide is for contributors and maintainers managing the Madhyamakist organization's static site hosted via GitHub Pages and deployed on a custom domain.

---

## 🚀 Hosting Overview

- **Repo**: [madhyamakist.github.io](https://github.com/madhyamakist/madhyamakist.github.io)
- **Site URL**: https://www.madhyamakist.com
- **Platform**: GitHub Pages
- **Domain Registrar**: GoDaddy
- **Custom Domain**: `www.madhyamakist.com`

---

## 🛠️ Initial Setup Instructions

### 1. ✅ Repository Naming

To use GitHub Pages with a custom domain for an **organization site**, the repo must be named:

madhyamakist.github.io

This tells GitHub to serve it from:

https://madhyamakist.github.io/

---

### 2. 🌍 DNS Configuration (GoDaddy)

#### A Records
Set 4 A records for the root domain `@`:

| Type | Name | Value             |
|------|------|-------------------|
| A    | @    | 185.199.108.153   |
| A    | @    | 185.199.109.153   |
| A    | @    | 185.199.110.153   |
| A    | @    | 185.199.111.153   |

These are GitHub server IPs.

#### CNAME Record
Set a CNAME for `www` pointing to GitHub Pages:

| Type  | Name | Value                  |
|-------|------|------------------------|
| CNAME | www  | madhyamakist.github.io |

---

### 3. 🌐 GitHub Pages Configuration

In the GitHub repo:
- Go to **Settings → Pages**
- Set the source to the main branch (e.g. `main`) and `/docs`
- In the **Custom Domain** field, enter:

www.madhyamakist.com

- ✅ Enable **"Enforce HTTPS"**

---

### 4. 📝 CNAME File

Add a `CNAME` file in the repo root with one line:

www.madhyamakist.com

This ensures GitHub recognizes and serves the site under the custom domain.

---

## 🔒 HTTPS & SSL Notes

- GitHub Pages provides SSL automatically (via Let’s Encrypt).
- DNS and HTTPS configuration may take up to **30 minutes** to propagate.


## 🛑 Common Issues

| Issue                             | Solution                                                                 |
|----------------------------------|--------------------------------------------------------------------------|
| Page not loading after changes   | Wait for DNS propagation (can take a few minutes to a few hours)        |

---

## 👩‍🔧 Maintainer Tips

- Avoid using subfolders for deployment (`/madhyamakist/`) — this guide assumes root-level Pages deployment.
- For major changes, test on a fork or separate branch and preview with GitHub Pages.

---

## 📫 Contact / Help

For issues with the live domain or deployment process, open an issue on the [GitHub repo](https://github.com/madhyamakist/madhyamakist.github.io) or contact the current maintainer.
