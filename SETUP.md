# Alan Biju Portfolio — Setup Guide

## Folder Structure
```
portfolio/
├── index.html          ← Your portfolio (this is the whole site)
├── SETUP.md            ← This file
└── resume/
    └── alan-biju-resume.pdf   ← DROP YOUR PDF HERE
```

---

## Step 1 — Add Your Resume PDF

1. Export your resume as a PDF
2. Rename it: `alan-biju-resume.pdf`
3. Place it in the `resume/` folder

The "↓ Resume" button in the nav will automatically download it.

---

## Step 2 — Set Up EmailJS (contact form)

This is completely free. Takes ~5 minutes.

### 2a. Create an EmailJS account
Go to https://www.emailjs.com and sign up (free tier = 200 emails/month)

### 2b. Connect your Gmail
1. Dashboard → **Email Services** → Add New Service
2. Choose **Gmail**
3. Connect `alanbiju3002@gmail.com`
4. Copy the **Service ID** (looks like `service_xxxxxxx`)

### 2c. Create an email template
1. Dashboard → **Email Templates** → Create New Template
2. Set it up like this:

**Subject:**
```
New message from {{from_name}} via Portfolio
```

**Body:**
```
You have a new message from your portfolio contact form.

Name:    {{from_name}}
Email:   {{from_email}}
Company: {{company_role}}

Message:
{{message}}
```

3. Set **Reply To:** `{{reply_to}}`
4. Save. Copy the **Template ID** (looks like `template_xxxxxxx`)

### 2d. Get your Public Key
1. Dashboard → **Account** → **General** tab
2. Copy your **Public Key**

### 2e. Paste into index.html
Open `index.html`, find these 3 lines near the bottom and replace:

```javascript
const EMAILJS_PUBLIC_KEY  = 'YOUR_PUBLIC_KEY';   // ← paste here
const EMAILJS_SERVICE_ID  = 'YOUR_SERVICE_ID';   // ← paste here
const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID';  // ← paste here
```

**Example (yours will be different):**
```javascript
const EMAILJS_PUBLIC_KEY  = 'abc123XYZdef456';
const EMAILJS_SERVICE_ID  = 'service_a1b2c3d';
const EMAILJS_TEMPLATE_ID = 'template_x9y8z7w';
```

---

## Step 3 — Deploy to GitHub Pages (free hosting)

1. Create a GitHub repo named: `alanbiju2003.github.io`
   (must match your GitHub username exactly)

2. Push all files:
```bash
git init
git add .
git commit -m "Portfolio launch"
git branch -M main
git remote add origin https://github.com/alanbiju2003/alanbiju2003.github.io.git
git push -u origin main
```

3. Go to repo **Settings → Pages → Source: Deploy from branch → main**

Your portfolio will be live at: **https://alanbiju2003.github.io**

---

## Alternatively — Any Static Host Works

| Host | Free | Command |
|------|------|---------|
| GitHub Pages | ✅ | Push to `username.github.io` repo |
| Netlify | ✅ | Drag & drop the folder at netlify.com/drop |
| Vercel | ✅ | `npx vercel` in the folder |
| Cloudflare Pages | ✅ | Connect GitHub repo |

---

## Updating Your Portfolio

Just edit `index.html` — everything is in one file. Push to GitHub and it auto-deploys.

To update project GitHub links, search for `https://github.com/alanbiju2003` and replace with your specific repo URLs.
