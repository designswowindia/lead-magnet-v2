# lead-magnet-v2
WordPress Lead Magnet plugin — homepage popup with international phone picker, one-day cookie guard, WP database storage, and a full admin leads grid with CSV import/export.
# WordPress Lead Capture Plugin
> **Capture leads. Store them locally. Deliver your freebie — zero third-party CRM required.**

---

## ✨ What is Lead Magnet?

**Lead Magnet** is a lightweight WordPress plugin that displays a beautifully styled popup on your homepage, collects visitor information (name, email, mobile), stores every lead directly in your WordPress database, and instantly unlocks a PDF download — all without a single external CRM subscription.

Built for creators, agencies, coaches, and small businesses who want a **self-hosted, privacy-first lead capture flow** without Mailchimp, HubSpot, or any third-party dependency.

---

## 🚀 Features

### 🎯 Frontend Popup
- Elegant **600 × 400 px two-column popup** — inherits your theme's colours automatically
- Appears **0.8 s after page load** — smooth fade-in animation
- **Once-per-day cookie guard** — never annoys the same visitor twice
- Closeable via ✕ button, Cancel button, overlay click, or `Escape` key
- Fully **accessible** — ARIA roles, labelled fields, live alert region

### 📋 Smart Lead Form
| Field | Required | Notes |
|---|---|---|
| Full Name | ✅ Yes | Max 60 characters |
| Email | ❌ Optional | Validated if provided |
| Mobile Number | ✅ Yes | With international country-code selector (190+ countries) |

- Dual-layer validation: **client-side** (instant UX feedback) + **server-side** (secure fallback)
- Mobile stored in international format: `+91 9876543210`
- Download button activates **only after successful submission** — no skipping the form

### 📦 PDF Delivery
- Configure your PDF URL directly from **WordPress Media Library** — no external hosting needed
- Download triggered programmatically after lead is saved

### 🛡️ Security First
- **Nonce verification** on every AJAX call and admin form
- All inputs sanitised with WordPress core functions (`sanitize_text_field`, `sanitize_email`, `esc_url_raw`)
- `ABSPATH` guard on every file — no direct file execution

### 🗄️ WordPress-Native Data Storage
- Creates a **custom DB table** (`wp_lm_leads`) on activation using `dbDelta`
- Zero external API calls — your lead data stays on your server
- No recurring SaaS fees

### ⚙️ Admin Panel — Settings
- Set your **popup heading text** (default: `"Get Your Free Guide"`)
- Pick your **PDF file** from the WordPress Media Library with a visual picker

### 📊 Admin Panel — Leads Grid
| Feature | Details |
|---|---|
| Search | Filter leads by name, email, or mobile |
| Date Range Filter | Defaults to last 7 days; fully customisable |
| Pagination | 10 leads per page |
| Add Lead | Manually add leads from admin |
| Edit Lead | Update any existing lead inline |
| Delete Lead | Single-row delete with confirmation prompt |
| CSV Import | Bulk-import leads via CSV upload |
| CSV Export | Download all leads as a `.csv` file |

---

## 📁 Plugin Structure

```
lead-magnet/
├── lead-magnet.php          # Main plugin file — constants, hooks, activation, AJAX
├── admin/
│   └── admin-page.php       # Admin menu, settings page, leads grid
├── assets/
│   ├── css/
│   │   ├── lead-magnet.css  # Frontend popup styles
│   │   └── lm-admin.css     # Admin panel styles
│   └── js/
│       ├── lead-magnet.js   # Frontend: popup logic, validation, AJAX, download
│       └── lm-admin.js      # Admin: media picker, AJAX actions
└── README.txt               # WordPress.org-style readme
```

---


### After Activation
1. Navigate to **Lead Magnet → Settings** in the admin sidebar.
2. Set your **Popup Heading Text** (e.g. `"Download Your Free Checklist"`).
3. Click **Select PDF** to pick your PDF from the Media Library (or paste a direct URL).
4. Save Settings.
5. Visit your homepage — the popup appears after **0.8 seconds**. 🎉

> **Tip:** Clear cookies or use a private/incognito window to see the popup again during testing (it sets a 1-day cookie after first view).

---


## ⚙️ Requirements

| Requirement | Minimum |
|---|---|
| WordPress | 5.8 |
| PHP | 7.4 |
| MySQL | 5.6 / MariaDB 10.1 |
| jQuery | Bundled with WordPress |

---


## 📤 CSV Import Format

When importing leads via the admin panel, your CSV file should follow this structure:

```csv
full_name,email,mobile_number
Jane Doe,jane@example.com,+91 9876543210
John Smith,,+1 5551234567
```

- **Header row required.**
- `email` column can be left empty (field is optional).
- `mobile_number` should include the country dialling code.

---


## 🔒 Security Notes

- All frontend-submitted data is sanitised server-side before DB insertion.
- Nonces are rotated per session — replay attacks are not possible.
- Admin capabilities are checked with `current_user_can('manage_options')` before rendering any admin UI.
- No data is transmitted to external servers.

---

## 📜 Changelog

### v2.0
- Complete rewrite from scratch
- Leads now stored in WordPress DB — no external CRM dependency
- International phone number selector (190+ country codes)
- Email field changed to optional
- Full Leads Grid admin page: search, date filter, pagination, add, edit, delete, CSV import/export
- Configurable popup heading text
- Improved popup design: 600 × 400 px two-column layout with theme-aware colours
- Nonce verification on all forms and AJAX calls

---

## 👤 Source

**Author**  : Akhilesh Maurya 

**Email**   : info@designswow.com | designswowindia@gmail.com

**Company** : https://designswow.com

**Download**  : https://drive.google.com/file/d/1YVXpJ_srFRXd1sTaj9Jnsj-DzJ7TGTq4/view?usp=sharing

---

If this plugin helped you, consider leaving a ⭐ on the repository — it helps others discover it!

For bug reports and feature requests, please [open an issue](#).
