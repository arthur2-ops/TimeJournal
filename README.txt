TIME JOURNAL

A single-page web app — no build step, no backend. Everything (index.html,
butterfly.png, manifest.json, sw.js, icons) is a plain static file.

WHAT'S NEW IN THIS BUILD
- Installable as an app on iPhone (Add to Home Screen) and works offline
  once loaded, via manifest.json + sw.js (a service worker).
- Data still lives in the browser's localStorage, per device/browser —
  your iPhone and your Mac will each keep their own separate entries
  unless you wire up real cloud sync later.

------------------------------------------------------------
GO LIVE — PUT IT ON THE REAL INTERNET (free, ~2 minutes)
------------------------------------------------------------
Pick ONE of these. All are free and give you a public https:// URL that
works on your phone and your Mac, without your Mac needing to stay on.

Option A — Netlify Drop (fastest, no account strictly required)
  1. Go to https://app.netlify.com/drop
  2. Drag this whole folder (all files, unzipped) onto the page.
  3. Netlify gives you a live URL like https://random-name.netlify.app
  4. (Optional) Create a free account to keep the site permanently and
     rename it.

Option B — GitHub Pages (best if you already use GitHub)
  1. Create a new repo, e.g. "time-journal".
  2. Upload all the files in this folder to the repo (root, not a subfolder).
  3. Repo Settings -> Pages -> Deploy from branch -> main / (root).
  4. Your site appears at https://YOUR-USERNAME.github.io/time-journal/

Option C — Vercel
  1. https://vercel.com -> New Project -> "Deploy without Git" / drag-and-drop
     this folder, or connect a repo containing these files.
  2. Vercel gives you a URL like https://time-journal.vercel.app

Any of these works — pick whichever feels easiest. Once it's live:

ON YOUR IPHONE
  1. Open the live URL in Safari.
  2. Tap Share -> Add to Home Screen.
  3. It now opens full-screen like a real app, with its own icon, and
     keeps working even with no signal (offline caching).

ON YOUR MAC
  1. Just open the live URL in any browser and use it there.
  2. In Safari you can also do File -> Add to Dock (macOS Sonoma+) for an
     app-like launch icon.

------------------------------------------------------------
LOCAL TESTING (no internet, same Wi-Fi only)
------------------------------------------------------------
1. On your Mac, in this folder, run:
     python3 -m http.server 8000
2. Find your Mac's local IP (System Settings -> Wi-Fi -> Details), e.g.
   192.168.1.20.
3. On your iPhone, on the same Wi-Fi, open http://YOUR-MAC-IP:8000
4. Safari -> Share -> Add to Home Screen.
   Note: this only works while your Mac is on, awake, and running that
   command — Option A/B/C above give you a permanent link instead.

------------------------------------------------------------
NOTES
------------------------------------------------------------
- Manual time logging with automatic categorisation, and editable
  categorisation rules.
- Excel/CSV import.
- Apple Health demo connection (Sleep + Exercise only). This browser demo
  can't access real Apple Health data — a native iPhone build would use
  HealthKit permissions instead.
- Google Sheets import via a published CSV URL (a production build could
  use Google OAuth for private sheets instead).
- Year Calendar view and a dated Notes section, both stored locally.
- All data persists in the browser's localStorage — clearing site data/
  history, or switching browsers/devices, starts fresh.
