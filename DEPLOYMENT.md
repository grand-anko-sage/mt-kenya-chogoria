# Deploying Mt Kenya Chogoria App

## What's Improved in This Version
- ✅ WhatsApp quick-contact button on every guide card
- ✅ Rich pre-filled WhatsApp booking message sent to the specific guide
- ✅ M-Pesa Paybill payment panel shown in booking form (preview)
- ✅ Full step-by-step M-Pesa payment instructions on confirmation screen
- ✅ Copy-to-clipboard buttons for Paybill, Account No, and Deposit amount
- ✅ M-Pesa deposit info shown on every booking card in "My Bookings"
- ✅ WhatsApp buttons per booking (to guide AND to coordinator)
- ✅ Voucher downloads as readable .txt file (not JSON)
- ✅ SPA routing fixed for Vercel & Netlify

---

## Option A — Deploy on Vercel (Recommended)

1. Push your project to GitHub (or GitLab / Bitbucket).
2. Go to https://vercel.com → **New Project** → Import your repo.
3. Vercel auto-detects Vite. Leave all build settings as default.
4. Click **Deploy**. Done — live in ~60 seconds.

**If you add Gemini AI later**, add env vars in:
Vercel Dashboard → Project → Settings → Environment Variables
```
VITE_GEMINI_API_KEY = your_key_here
```

---

## Option B — Deploy on Netlify

1. Push to GitHub.
2. Go to https://app.netlify.com → **Add new site** → Import from Git.
3. Build command: `npm run build`
4. Publish directory: `dist`
5. Click **Deploy site**.

The `public/_redirects` file already handles SPA routing for you.

---

## Run Locally

```bash
npm install
npm run dev
# → http://localhost:3000
```

## Build for Production

```bash
npm run build
# Output in /dist — upload this folder anywhere
```

---

## M-Pesa Paybill (Current Setup)
The app uses **Paybill 4037832** for demonstration.
To use your real M-Pesa Paybill:
1. Register on Safaricom Daraja: https://developer.safaricom.co.ke
2. Get your Paybill/Business Shortcode
3. Update `MPESA_PAYBILL` constant in:
   - `src/components/GuideBooking.tsx` (line ~11)
   - `src/components/MyBookings.tsx` (line ~17)

