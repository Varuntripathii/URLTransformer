# URL Transformer

A lightweight, single-file web app that rewrites remote URLs to point to your local development environment — instantly, with no install required.

---

## What It Does

When working with applications that generate session-based or redirect URLs pointing to a remote server, you often need to remap those URLs to your local machine for testing. This tool does exactly that.

Paste in a URL like:

```
https://advantagetouch.stayinfrontadvantage.com/AdvantageTouchCG/sfweb/HandleSessionToken?token=AQBEkZBy6tkyTrZy/MXCnh1ZBVQAbwB1AGMAaAA=&originalURL=https://advantagetouch.stayinfrontadvantage.com/AdvantageTouchCG/
```

And it transforms it to:

```
http://localhost/AdvantageTouchCG/sfweb/HandleSessionToken?token=AQBEkZBy6tkyTrZy/MXCnh1ZBVQAbwB1AGMAaAA=&originalURL=http://localhost/AdvantageTouchCG/
```

It replaces **every occurrence** of the remote hostname — including ones embedded inside query parameters like `originalURL=` — so the entire URL is consistently rewritten in one shot.

---

## Features

- Works with **any remote hostname** and **any app path** — not hardcoded to a specific domain
- Rewrites **nested URLs** inside query parameters automatically
- Configurable **target host** (default: `localhost`) and **protocol** (default: `http`)
- One-click **Copy to Clipboard** — works in `file://`, HTTP, and HTTPS environments
- `Ctrl+Enter` keyboard shortcut to trigger the transform
- No dependencies, no build step, no install — just open the HTML file

---

## How to Use

1. Open `index.html` in any browser
2. Paste your remote URL into the input box
3. Set your desired **host** and **protocol** if different from the defaults
4. Click **Transform URL** (or press `Ctrl+Enter`)
5. Click **Copy** to copy the result to your clipboard

---

## Configuration

| Field | Default | Description |
|---|---|---|
| Replace host with | `localhost` | The hostname to substitute in the URL |
| New protocol | `http` | The protocol to use (`http` or `https`) |

---

## Deployment

Since this is a pure HTML/CSS/JS file with no backend, it can be hosted anywhere static files are supported.

**Vercel (recommended)**

1. Rename the file to `index.html` and place it in a folder
2. Go to [vercel.com](https://vercel.com) and log in
3. Click **Add New → Project** and drag your folder onto the page
4. Click **Deploy** — you'll get a live URL in seconds

Alternatively, via the Vercel CLI:

```bash
npm install -g vercel
cd your-folder
vercel
```

---

## Tech Stack

- Plain HTML, CSS, and JavaScript
- No frameworks, no dependencies, no build tools
- Single file — everything is self-contained

---

## License

Free to use and modify.
