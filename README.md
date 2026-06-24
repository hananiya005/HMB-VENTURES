# HMB Ventures Website — Setup Guide

## Files Included
```
hmb-site/
├── index.html          ← Main homepage
├── blog.html           ← Blog page
├── portal.html         ← Client portal login
├── portal-dashboard.html ← Client dashboard
├── privacy.html        ← Privacy policy
├── terms.html          ← Terms of service
├── logo.png            ← Your logo (already included)
├── netlify.toml        ← Netlify config
├── css/
│   └── style.css       ← All styles
└── js/
    └── main.js         ← All JavaScript
```

---

## STEP 1 — Set Up EmailJS (Free — takes 5 minutes)

1. Go to https://www.emailjs.com and create a free account
2. Click **Add New Service** → choose **Gmail** → connect your `hmbventures@gmail.com`
3. Note your **Service ID** (e.g. `service_abc123`)
4. Click **Email Templates** → **Create New Template**
5. Set the template to:
   ```
   Subject: New Inquiry from {{from_name}} — HMB Ventures

   Name: {{from_name}}
   Email: {{from_email}}
   Phone: {{phone}}
   Company: {{company}}
   Service: {{service}}
   Budget: {{budget}}

   Message:
   {{message}}
   ```
6. Save. Note your **Template ID** (e.g. `template_xyz789`)
7. Go to **Account** → copy your **Public Key**
8. Open `js/main.js` and update lines 8–10:
   ```js
   const EMAILJS_SERVICE_ID  = 'service_abc123';   // ← your Service ID
   const EMAILJS_TEMPLATE_ID = 'template_xyz789';   // ← your Template ID
   const EMAILJS_PUBLIC_KEY  = 'your_public_key';   // ← your Public Key
   ```

---

## STEP 2 — Deploy to Netlify (Free — takes 3 minutes)

### Option A: Drag & Drop (Easiest)
1. Go to https://app.netlify.com
2. Sign up free with your email or GitHub
3. On the dashboard, drag the entire `hmb-site` folder into the deploy area
4. Your site is live instantly! You'll get a URL like `https://hmb-ventures.netlify.app`

### Option B: Connect GitHub (Best for updates)
1. Upload the `hmb-site` folder to a GitHub repository
2. In Netlify: **Add new site** → **Import from Git** → connect your repo
3. Build settings: leave blank (static site)
4. Deploy!

---

## STEP 3 — Add a Custom Domain (Optional)
1. Buy a domain at Namecheap, GoDaddy, or Google Domains (e.g. `hmbventures.com`)
2. In Netlify: **Site settings** → **Domain management** → **Add custom domain**
3. Follow the DNS instructions — takes 10–30 minutes to go live
4. Netlify gives you **free HTTPS** automatically

---

## STEP 4 — Update Social Links
Open `index.html` and update these URLs with your real profiles:
- LinkedIn: `https://linkedin.com/company/hmbventures`
- Twitter/X: `https://twitter.com/hmbventures`
- Instagram: `https://instagram.com/hmbventures`

---

## Client Portal
- Demo login: `client@hmbventures.com` / `hmb2025`
- For real clients, you can use **Netlify Identity** (free) or upgrade to a backend
- All client inquiries for portal access go to your WhatsApp automatically

---

## Need Help?
If you get stuck on any step, WhatsApp the HMB Ventures team directly and we'll help you deploy it! 🚀
