# Keyrisk Email Signature Generator

Internal tool for generating branded email signatures for Keyrisk team members.

## Features

- Live preview with correct Keyrisk branding (logo, colours, fonts)
- Flexible mailbox checklist — tick any combination of links
- Quick presets: Standard, Bryte, Service Links
- Toggle between "Dedicated Mailboxes" and "Service Links" section heading
- Optional FAIS disclaimer for licensed roles
- Optional "Please include fund name..." note
- One-click "Copy Signature" → paste directly into Outlook / Gmail
- One-click "Copy HTML" for raw code
- Auto-generates email addresses as `flastname@keyrisk.co.za`

## Deployment

This is a static site — a single `index.html` file with embedded logo and watermark PNGs. No build step, no server, no dependencies.

### Deploy to Vercel via GitHub

1. Push this folder to a new GitHub repo
2. Go to [vercel.com/new](https://vercel.com/new)
3. Import your GitHub repo
4. Vercel auto-detects it as a static site — accept defaults
5. Click **Deploy**

Vercel will give you a URL like `keyrisk-signature.vercel.app`. Every push to the main branch will redeploy automatically.

### Local development

Just open `index.html` in a browser — no server required.

## File structure

```
keyrisk-signature/
├── index.html      # The entire app (HTML + CSS + JS + embedded logo/watermark)
├── vercel.json     # Vercel config (caching, security headers)
└── README.md       # This file
```

## Updating

To change the logo, colours, or mailbox options, edit `index.html`:

- **Logo & watermark** — search for `LOGO_SRC` and `WM_SRC` constants near the top of the `<script>` block
- **Mailbox options** — edit the `ALL_MAILBOXES` array
- **Quick presets** — edit the `PRESETS` object
- **Colours** — edit the CSS `:root` variables at the top

After any change, push to GitHub and Vercel will auto-deploy within ~30 seconds.
