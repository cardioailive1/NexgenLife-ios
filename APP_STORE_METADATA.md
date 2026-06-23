# NexGenLife — App Store Connect Submission Guide
# Corverxis Technologies Ltd

## App Information

| Field | Value |
|---|---|
| App Name | NexGenLife |
| Bundle ID | com.W9464NC4J7.nexgenlife |
| SKU | NEXGENLIFE-001 |
| Primary Language | English (U.K.) |
| Category | Business |
| Secondary Category | Medical |
| Content Rights | No third-party content |
| Age Rating | 4+ |
| Price | Free (IAP for subscriptions) |

---

## App Description (App Store listing)

NexGenLife is an AI-powered regulatory document platform built for life sciences professionals, startup founders, and enterprise pharma teams.

Generate regulatory-ready documents in minutes — FDA submissions, clinical trial protocols, drug development reports, QMS documentation, IP/patent strategy, and more — across 20+ global jurisdictions including FDA, EMA, MHRA, NMPA, CDSCO, NAFDAC, SAHPRA, and the African Medicines Agency.

**What NexGenLife does:**
• Generates regulatory-ready documents for medical devices, drugs, biologics, diagnostics, and digital health products
• Supports 20+ regulatory jurisdictions spanning every populated continent
• Exports to Word, Google Docs, and PDF in one tap
• Full user authentication with optional two-factor security
• Compliant document templates aligned to FDA, EMA, ICH, and ISO standards

**Plans:**
• Starter — 10 documents/month · 3 programmes · All 8 modules
• Professional — Unlimited documents · Priority support
• Enterprise — Private deployment · Custom AI · Dedicated specialist

No free trial. Subscription required.

---

## Subtitle (30 chars max)
AI Regulatory Documents

## Keywords (100 chars max)
FDA,EMA,regulatory,clinical trial,medical device,pharma,biotech,QMS,510k,submission

---

## In-App Purchases

### IAP 1 — Starter Plan
- Product ID: com.W9464NC4J7.nexgenlife.starter
- Type: Auto-Renewable Subscription
- Price: $99.00 / month
- Reference Name: NexGenLife Starter
- Display Name: Starter Plan
- Description: 10 document generations per month, 3 active programmes, all 8 regulatory modules.
- Subscription Group: NexGenLife Plans
- Free Trial: None

### IAP 2 — Professional Plan
- Product ID: com.W9464NC4J7.nexgenlife.professional
- Type: Auto-Renewable Subscription
- Price: $499.00 / month
- Reference Name: NexGenLife Professional
- Display Name: Professional Plan
- Description: Unlimited document generations, all regulatory modules, priority support.
- Subscription Group: NexGenLife Plans
- Free Trial: None

### IAP 3 — Enterprise Plan
- Product ID: com.W9464NC4J7.nexgenlife.enterprise
- Type: Contact Sales (not IAP — direct to support@corverxis.com)
- Note: Enterprise is a sales-led process. No IAP needed for this tier.

---

## App Review Information

### Demo Account (required)
Create a test account at https://nexgenlife.studio/ before submission:
- Email: reviewer@corverxis.com  ← create this before submitting
- Password: ReviewNGL2026!       ← set when creating the account
- Plan: You will need to manually grant paid access in Supabase for this account

### Notes for App Review Team
This app requires a paid subscription to access core features. A demo account with 
full Professional access has been provisioned above for review purposes. 

The app connects to:
- Supabase (authentication)
- Anthropic API (document generation)  
- Stripe (payment processing)
- Formspree (enterprise contact form)

All external connections use HTTPS.

---

## Support & Legal URLs

| Field | URL |
|---|---|
| Support URL | https://nexgenlife.studio |
| Marketing URL | https://nexgenlife.studio |
| Privacy Policy URL | https://nexgenlife.studio (privacy modal is embedded in the app) |

Note: Apple requires a publicly accessible Privacy Policy URL. 
Host the privacy policy content at a dedicated URL e.g. https://nexgenlife.studio/privacy
or use a free service like Notion/GitHub Pages before submitting.

---

## Screenshots Required

Apple requires screenshots for these device sizes:
- iPhone 6.9" (iPhone 15 Pro Max) — 1320 × 2868 px — REQUIRED
- iPhone 6.5" (iPhone 14 Plus) — 1284 × 2778 px — REQUIRED  
- iPad Pro 13" — 2064 × 2752 px — if supporting iPad
- iPad Pro 11" — 1668 × 2388 px — if supporting iPad

Recommended screenshots to capture:
1. Home/landing page with NexGenLife hero
2. Sign in / Create Account screen
3. Launch App — document type selector open
4. Active document being generated (streaming)
5. Completed document with export buttons (Word, PDF, Google Docs)
6. Paywall / Plan selection screen
7. Jurisdiction selector showing global coverage

Use Xcode Simulator to capture screenshots at correct dimensions.

---

## App Store Review Checklist

- [ ] Bundle ID matches: com.W9464NC4J7.nexgenlife
- [ ] Signing team set in Xcode → Signing & Capabilities
- [ ] Privacy Policy URL accessible publicly
- [ ] Demo account created and tested
- [ ] IAP products created in App Store Connect (Starter + Professional)
- [ ] IAP products submitted for review alongside app
- [ ] Screenshots captured at required sizes
- [ ] App icon set (1024×1024 PNG, no alpha channel, no rounded corners)
- [ ] Version set to 1.0.0, Build to 1
- [ ] All Info.plist permission strings added
- [ ] Tested on real device (not just simulator)
