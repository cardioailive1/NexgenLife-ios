# NexGenLife — iOS App (Capacitor)
### Corverxis Technologies Ltd

This folder wraps the NexGenLife web app in a native iOS shell using **Capacitor**.
The HTML file is NOT modified — it runs as-is inside a native WebView.

Building and submitting to the App Store requires a **Mac with Xcode**.
Everything here is the complete project scaffold — run the commands below on your Mac.

🌐 **Platform:** https://nesgenlife.studio  
🏢 **Company:** https://corverxis.com

---

## What's in this folder

| File/Folder | Purpose |
|---|---|
| `package.json` | Capacitor dependencies |
| `capacitor.config.json` | App ID, name, bundle ID, iOS settings |
| `www/index.html` | NexGenLife app (copied in, not modified) |
| `ios-info-plist-additions.xml` | Permission strings to paste into Info.plist |
| `APP_STORE_METADATA.md` | App Store Connect submission guide + IAP IDs |
| `README.md` | This file |

---

## Prerequisites (on your Mac)

1. **Xcode** — Install from the Mac App Store (free, ~10 GB)
2. **Node.js** — https://nodejs.org (LTS version)
3. **CocoaPods** — `sudo gem install cocoapods`
4. **Apple Developer Account** — https://developer.apple.com/programs/ ($99/year, required for App Store)
5. Your Apple ID team: **W9464NC4J7** (already set in `capacitor.config.json`)

---

## Step-by-Step Deployment

### Step 1 — Copy this folder to your Mac

```bash
cd nexgenlife-ios
npm install
```

### Step 2 — Add the iOS platform

```bash
npx cap add ios
```

This generates an `ios/` folder containing a full Xcode project.

### Step 3 — Sync the web app

```bash
npx cap sync ios
```

Run this again any time `www/index.html` is updated.

### Step 4 — Open in Xcode

```bash
npx cap open ios
```

---

## Step 5 — Configure Xcode (IMPORTANT)

### 5a — Signing
- Select **App** in the left sidebar → **Signing & Capabilities** tab
- Check **Automatically manage signing**
- Set **Team** to your Apple Developer team (W9464NC4J7)
- Bundle Identifier should already be: `com.W9464NC4J7.nexgenlife`

### 5b — Info.plist permissions
Open `ios/App/App/Info.plist` and add the keys from `ios-info-plist-additions.xml`.
The most important ones for App Review:

```xml
<key>NSCameraUsageDescription</key>
<string>NexGenLife uses the camera to attach supporting documents to your regulatory prompts.</string>

<key>NSPhotoLibraryUsageDescription</key>
<string>NexGenLife accesses your photo library to attach reference images to regulatory submissions.</string>

<key>NSFaceIDUsageDescription</key>
<string>NexGenLife uses Face ID for quick, secure sign-in to protect your regulatory documents.</string>
```

### 5c — App Icon
- Create a **1024×1024 PNG** icon (no alpha channel, no rounded corners — Apple applies the mask)
- In Xcode → Assets.xcassets → AppIcon → drag your icon to the 1024×1024 slot
- Xcode will auto-generate all required sizes

### 5d — Launch Screen / Splash
- Background colour is set to `#0B1725` (NexGenLife dark navy) in `capacitor.config.json`
- Optionally add a splash logo image via `@capacitor/splash-screen` plugin

---

## Step 6 — Set up In-App Purchases in App Store Connect

Go to https://appstoreconnect.apple.com → Your App → In-App Purchases → +

| Product | Product ID | Type | Price |
|---|---|---|---|
| Starter Plan | com.W9464NC4J7.nexgenlife.starter | Auto-Renewable Subscription | $99.00/mo |
| Professional Plan | com.W9464NC4J7.nexgenlife.professional | Auto-Renewable Subscription | $499.00/mo |

- Create a **Subscription Group** called: `NexGenLife Plans`
- Add both products to this group
- Set **no free trial** for both
- Submit IAP items for review alongside the app

> Note: Enterprise plan is sales-led — contact support@corverxis.com or visit https://corverxis.com. No IAP needed for this tier.

---

## Step 7 — Test on Device / Simulator

```bash
# In Xcode, select a simulator (iPhone 15 Pro recommended) and press ▶
# Or plug in a real iPhone and select it as the run target
```

Test these flows before submitting:
- [ ] Sign up with a new account
- [ ] Privacy Policy modal opens correctly
- [ ] Sign in / Sign out works
- [ ] Plan selection paywall appears
- [ ] Stripe checkout opens in Safari (external browser)
- [ ] Enterprise "Contact Sales" form submits
- [ ] Document generation works (requires valid API key in app)
- [ ] Word / PDF export buttons work
- [ ] 2FA setup and login flow

---

## Step 8 — Archive & Upload to App Store

1. In Xcode → **Product → Archive**
2. Wait for build to complete → **Distribute App**
3. Choose **App Store Connect** → **Upload**
4. Follow prompts — Xcode handles signing and packaging

### Then in App Store Connect:
1. Select your uploaded build
2. Fill in: Description, Keywords, Screenshots (see `APP_STORE_METADATA.md`)
3. Set Privacy Policy URL to: `https://nesgenlife.studio`
4. Set Marketing URL to: `https://corverxis.com`
5. Add demo account credentials for App Review team
6. Submit for review

Average App Store review time: **24–48 hours**

---

## Updating the App

When `nexgenlife.html` is updated:
```bash
cp /path/to/nexgenlife.html www/index.html
npx cap sync ios
# Then archive and upload a new build in Xcode
# Increment CFBundleVersion each time (1 → 2 → 3…)
```

---

## Common Issues

| Problem | Fix |
|---|---|
| `pod install` fails | Run `sudo gem install cocoapods` then `cd ios/App && pod install` |
| Signing error | Make sure your Apple Developer account is active and selected in Xcode |
| Stripe checkout doesn't open | Check `allowNavigation` in `capacitor.config.json` includes `*.stripe.com` |
| Supabase auth fails | Ensure HTTPS is used (not HTTP) — already configured |
| App rejected for privacy | Make sure all Info.plist `NSxxxxUsageDescription` strings are present |
| White screen on launch | Run `npx cap sync ios` after any changes to `www/` |

---

## Support

**Corverxis Technologies Ltd**  
📧 support@corverxis.com  
🌐 https://nesgenlife.studio  
🏢 https://corverxis.com
