# ✨ The Eras Tour — Karaoke Night Website

A 3-page voting website for your Taylor Swift Eras Tour karaoke night. Votes sync in real time across all devices via **JSONBin.io** (free).

---

## Pages

| File | Description |
|---|---|
| `index.html` | Welcome page with event info |
| `setlist.html` | Vote every Eras Tour song Sing or Skip — votes accumulate from all phones |
| `surprise.html` | Vote on the surprise song from Taylor's full discography |

---

## ⚡ Step 1 — Set Up JSONBin (free, ~2 minutes)

JSONBin is a free cloud JSON store — it acts as a tiny database so everyone's votes sync in real time.

1. Go to **[jsonbin.io](https://jsonbin.io)** and click **Sign Up** (free tier is fine)
2. After logging in, click **+ Create Bin** in the left sidebar
3. In the editor, paste this as the initial content and click **Create**:
   ```json
   { "setlist": {}, "surprise": {} }
   ```
4. Copy the **Bin ID** shown at the top of the page (it looks like `66a1b2c3d4e5f6a7b8c9d0e1`)
5. Click your profile icon → **API Keys** → copy your **Master Key** (starts with `$2a$10$...`)

---

## ⚡ Step 2 — Add Your Credentials to the HTML Files

Open **`setlist.html`** and **`surprise.html`** in any text editor (Notepad, TextEdit, VS Code, etc.).

Near the top of the `<script>` tag in each file, find this block:

```javascript
// ═══════════════════════════════════════════════════════════════
//  ✦  CONFIG — Paste your JSONBin credentials below  ✦
// ═══════════════════════════════════════════════════════════════
const BIN_ID  = '';   // e.g. '66a1b2c3d4e5f6a7b8c9d0e1'
const API_KEY = '';   // e.g. '$2a$10$ABCDEFGHIJKLMNOPQRSTUVWXabcdefghijklmn'
```

Fill in both values between the quotes, like this:

```javascript
const BIN_ID  = '66a1b2c3d4e5f6a7b8c9d0e1';
const API_KEY = '$2a$10$ABCDEFGHIJKLMNOPQRSTUVWXabcdefghijklmn';
```

Save both files. That's it — both pages share the same bin so votes sync across all devices instantly.

---

## ⚡ Step 3 — Host on GitHub Pages (free)

1. Go to [github.com](https://github.com) → **Sign Up** (or log in)
2. Click **+** → **New repository** → name it `eras-karaoke` → set to **Public** → **Create**
3. Click **Add file → Upload files** and upload all three HTML files
4. Go to **Settings → Pages → Source → Deploy from branch → main → Save**
5. Wait ~60 seconds, refresh — your URL will be:

```
https://YOUR-USERNAME.github.io/eras-karaoke/
```

Share this link with your group before the night! 🎉

---

## ✏️ Customise the Event Info

Open `index.html`, find these two lines around line 100, and replace the placeholder text:

```html
<div class="info-value">Update Me!</div>   ← your date
<div class="info-value">Your Place!</div>  ← your venue
```

---

## 🔄 How Syncing Works

- Every vote is written to JSONBin immediately
- All pages auto-refresh votes every **20 seconds**
- Use the **🔄 Sync Now** button to force an instant refresh
- If the internet drops, votes fall back to local browser storage automatically
- A coloured badge in the top-right corner shows sync status:
  - 🟢 **Synced** — all good
  - 🟡 **Syncing…** — request in progress
  - 🔴 **Offline** — network issue, votes saved locally
  - ⚫ **Local only** — credentials not configured yet

---

## 🎤 Night Format Suggestion

1. **Share the link before the night** so friends can vote in advance
2. **At the start:** open `setlist.html` → **View Results** to see the crowd's picks
3. Work through the winning songs **era by era** in setlist order
4. Finish with the **Surprise Song** — the wildcard voted for on page 3!

---

Made with ✨ for Swifties everywhere. JSONBin free tier allows 10,000 requests/month — more than enough for any karaoke night.
