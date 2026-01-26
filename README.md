# Steem Scanner Ecosystem

This repository powers the **Steem Scanner Ecosystem page**, a curated directory of applications, tools, games, and services built on the **Steem blockchain**.

The data in this repository is consumed directly by the Steem Scanner website and rendered live at:

👉 **[https://steemscanner.com/ecosystem](https://steemscanner.com/ecosystem)**

If you’re building something on Steem and want visibility, this is the canonical place to register your app.

---

## 📦 Repository Purpose

* Acts as a **single source of truth** for Steem ecosystem applications
* Provides a **machine-readable registry** via `ecosystem.json`
* Enables **community-driven curation** through GitHub pull requests
* Automatically powers the ecosystem listing on Steem Scanner

No centralized gatekeeping. Just structured data, versioned in public.

---

## 📁 Repository Structure

```
/
├── ecosystem.json   ← Main ecosystem registry (loaded by the website)
└── README.md        ← This file
```

Only one file matters for listings: **`ecosystem.json`**.

---

## 🧠 How It Works

* `ecosystem.json` contains a list of applications built on Steem
* Steem Scanner fetches this file directly from GitHub
* Any merged pull request updates the ecosystem page automatically
* No backend approval flow — GitHub history is the audit trail

Think of it as DNS, but for Steem apps.

---

## ➕ How to Add Your App

To list your app on **steemscanner.com/ecosystem**, follow these steps:

### 1. Fork the Repository

Fork this repo to your own GitHub account.

### 2. Edit `ecosystem.json`

Open `ecosystem.json` and add a new object inside the `applications` array.

**Do not remove or modify existing entries unless fixing an error.**

### 3. Follow the Required Schema

Each app entry must include **all** of the following fields:

```json
{
  "id": "unique-app-id",
  "name": "Your App Name",
  "managedBy": "@your-steem-username",
  "urls": {
    "website": "https://yourwebsite.com",
    "app": "https://yourapp.com"
  },
  "imageUrl": "https://link-to-your-logo.png",
  "about": "A clear and concise description of what your app does on the Steem blockchain.",
  "tags": ["category1", "category2", "category3"],
  "status": "active"
}
```

---

## 🧩 Field Guidelines

### `id`

* Must be **unique**
* Use lowercase and hyphens
* Example: `steem-predicts`, `my-awesome-app`

### `name`

* Human-readable app name
* Keep it clean and recognizable

### `managedBy`

* One or more Steem usernames
* Format: `@username` or `@user1, @user2`

### `urls`

* `website`: marketing or landing page
* `app`: direct app URL (can be the same)

### `imageUrl`

* Square image preferred (logo or app icon)
* Hosted image URL (SteemitImages, CDN, or your own domain)

### `about`

* 1–3 sentences
* Explain **what it does**, **who it’s for**, and **why it matters**
* This text is shown directly on the ecosystem page

### `tags`

* Relevant keywords only
* Examples: `gaming`, `defi`, `explorer`, `analytics`, `dao`, `nft`
* Avoid spammy or unrelated tags

### `status`

* Use `"active"` for live apps
* Future values may include `"beta"` or `"inactive"`

---

## ✅ Submission Checklist

Before opening a pull request, make sure:

* ✅ JSON is valid (no trailing commas)
* ✅ App is actually built on Steem
* ✅ URLs are working
* ✅ Description is clear and honest
* ✅ You didn’t edit other apps

Pull requests that break the JSON or include incomplete entries may be rejected.

---

## 🔀 Submit a Pull Request

Once your changes are ready:

1. Commit your changes
2. Open a **Pull Request** to the `main` branch
3. Briefly describe your app in the PR message

After review and merge, your app will appear automatically on:

👉 **[https://steemscanner.com/ecosystem](https://steemscanner.com/ecosystem)**

---

## 🧪 Local Testing (Optional)

You can validate the JSON format using any JSON validator or by running:

```
jsonlint ecosystem.json
```

Clean JSON keeps the ecosystem alive.

---

## 🤝 Governance & Curation

* This is a **community-maintained registry**
* Spam, scams, or misleading apps will be removed
* Maintainers may request clarification or edits
* All changes are transparent via GitHub history

The goal is trust, discoverability, and long-term ecosystem health.

---

## 🌱 Why This Exists

Blockchains don’t fail from lack of tech.
They fail from lack of **maps**.

This repository is a living map of what Steem builders are actually shipping.

Build boldly.
List responsibly.
Keep the ecosystem legible.

* Add a JSON Schema file for validation
* Create a GitHub Action to auto-lint PRs
* Design a submission badge (“Listed on Steem Scanner”)
* Extend this into a multi-chain ecosystem format
