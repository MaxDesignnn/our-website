# Our Website 💕 (pixel / vaporwave edition · 中文)

A little gift site with a retro 90s pixel-computer look: chunky "windows", a Chinese **pixel font**
(Zpix), a neon synthwave grid, and pixel-art hearts. All the on-screen text is in **Mandarin**.
It has a **"Play Our Song"** button (播放我们的歌) that opens NetEase Cloud Music, and a **world map**
connecting **Seoul (首尔)** and **Hamburg (汉堡)** with your live local times and the distance between you.

## 📂 Files (upload ALL of these)

- `index.html` — the page
- `zpix-subset.woff2` — **the pixel Chinese font (required!).** Without it the Chinese text falls
  back to an ordinary font and loses the pixel look. Keep it next to `index.html`.
- `README.md` — this file (optional)

## ✏️ How to personalize (edit `index.html`)

Open `index.html` and find the **`CONFIG`** block near the bottom (inside `<script>`).
You only ever need to touch that block.

1. **Add your song.** Paste your NetEase share link (or just the song id number):
   ```js
   songLink: "https://music.163.com/song?id=1234567",
   ```
   To get it: open the song in NetEase → *Share* → *Copy link*.

2. **Set the two of you.** `person1` is **him** (Seoul), `person2` is **you** (Hamburg).
   Change the `name`/`city` values if you like:
   ```js
   person1: { name: "你", city: "首尔", lat: 37.5665, lon: 126.9780, tz: "Asia/Seoul"    }, // him
   person2: { name: "我", city: "汉堡", lat: 53.5511, lon: 9.9937,   tz: "Europe/Berlin" }, // you
   ```
   ⚠️ If you type **new** Chinese characters that weren't already on the page, they may not show
   (the font only includes the characters currently used). Tell me and I'll rebuild the font subset.

3. **(Optional) Change the words** — `heroTitle` (给你) and `heroSub` (两座城市，一颗心).

## 🚀 Put it online with GitHub Pages

1. Create a new repository on GitHub (e.g. `our-website`).
2. Upload **`index.html` and `zpix-subset.woff2`** (and this `README.md`) to it.
3. In the repo: **Settings → Pages → Build and deployment → Source: `Deploy from a branch`**,
   pick branch `main` and folder `/ (root)`, then **Save**.
4. Wait ~1 minute. Your site is live at:
   `https://<your-username>.github.io/our-website/`

## 📝 Notes

- On a phone with the NetEase Cloud Music app installed, the button tries to open the app
  directly (`orpheus://` scheme). If that doesn't work, it falls back to the NetEase web page,
  which also offers an "Open in app" option.
- The map uses the free Leaflet + CARTO dark tiles from a CDN (needs internet, which GitHub Pages
  has). The pixel font is **self-hosted** (`zpix-subset.woff2`), so it doesn't depend on any CDN.
