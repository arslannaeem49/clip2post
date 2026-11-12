# Clip2Post — Start Here 🎬

Turn one long video into ready-to-post Shorts. Clip2Post listens to your
video (Whisper AI), finds the strongest moments, renders them as vertical
9:16 clips with burned-in captions, and prepares a full SEO pack
(5 titles, description, tags, hashtags) plus a thumbnail for every clip.
**Everything runs locally on your PC** — no uploads, no account, no cloud.

- **Free:** top 3 clips per video · 3 videos/day · 720p
- **Pro (license key):** all clips (up to 30 per video) · 1080p · SEO pack
  and thumbnails for every clip — **1 key = 1 PC**

---

## Where things live

Clip2Post installs per-user (no admin rights needed) at:

```
%LocalAppData%\Clip2Post
```

- Your projects live in `app\projects` inside that folder.
- Your license key is stored separately in `%APPDATA%\Clip2Post` —
  reinstalling the app never removes your activation.

---

## First-time setup (once)

1. Python is required. The setup prefers **Python 3.13** (3.12 / 3.11 also
   work). If you don't have it: install it from
   **https://www.python.org/downloads/** and make sure to tick
   **"Add python.exe to PATH"** during install.
2. Run **setup.bat** from the install folder (or tick *"Run first-time
   setup now"* at the end of the installer). It creates the environment,
   installs the exact package versions, checks for ffmpeg, and downloads
   the Whisper speech model (~140 MB) — internet is needed this once.
3. When you see **DONE**, setup is complete. Daily use works offline
   (except YouTube downloads and license checks).

---

## Everyday use

### 1. Launch
Use the **Clip2Post** desktop shortcut. A console window opens — **keep it
open, it is the engine** — and the interface appears in your browser at
`http://127.0.0.1:8791`.

> The page layout refreshes with every reload, but the engine only picks
> up changes when you close the console window and launch again. If a
> button ever behaves oddly, restart the app first.

### 2. Add a video
- **Local file:** paste the **full path** of the file
  (e.g. `C:\Users\You\Videos\talk.mp4`) — the file name alone is not enough.
- **YouTube:** paste the link of **one single video** — the **Share**
  button under the video gives the cleanest link.
  - Playlist or channel links are **refused on purpose** (they would
    download the whole list). A mix/radio link works, but only that one
    video is imported.
- Click **Import & Analyze**.

### 3. The progress strip
The strip at the bottom reports every stage: *Downloading → Transcribing
→ Finding clips → Rendering → SEO → Thumbnails.*
- Animated = working · **Solid green = Done ✓** · Red = failed or stopped
- **■ Stop** cancels any running job (download, analyze, render).

### 4. Clips and rendering
- Clips are ranked by score — higher is stronger.
- Render in two ways: **🎬 Render Top N** (all pending clips at once) or
  **🎬 Render this clip** inside a clip's Export panel.
- When a render finishes, the clip becomes **READY**, its **SEO Pack**
  appears automatically (5 title options, description, tags, hashtags),
  a thumbnail is generated, and the **Download** button shows up.
- The built-in **JFK demo project is view-only** — it ships with 3 clips
  ready-made and cannot render or be deleted. Rendering always happens
  in projects created from your own videos.

### 5. If you get 0 clips
That means **no speech was found** in the video (music, silence, songs).
Clips are made from spoken words — talks, stories, podcasts, commentary.
The app tells you this on screen and lets you play the source video to
check.

### 6. Managing projects
- Open any project from the sidebar list.
- **Delete:** hover over a project → click the **✕** → confirm. Its clips,
  renders and SEO packs are removed. The demo project and a project that
  is currently busy cannot be deleted (stop the job first).

### 7. Captions and Facecam
- Edit any clip's captions in the **Captions** panel and press **Save** —
  the edited text is what gets burned in at render time.
- **Facecam Reaction** currently shows a camera preview; recording your
  reaction into the clip arrives in a future update.

---

## License — going Pro

1. Open **License** in the app.
2. Paste your key — real keys look like this:
   `XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX`
   (copy the **"License key"** line from your order email — the order
   number is not the key).
3. Press **Activate**. When Pro is on you will see the **PRO** badge and
   *"All clips unlocked · up to 30 per video · 1080p exports"*.
4. **1 key = 1 PC.** To move to another PC, press **Deactivate** here first.
5. No internet? Pro keeps working for **14 days** (offline grace), then it
   checks in once when you are back online.
6. Never share a screenshot that shows your full live key.

Get Pro at **clip2post.lemonsqueezy.com** — Monthly $7 · Yearly $49 ·
Lifetime $39.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| A button exists but does nothing / page looks old | Press **Ctrl+F5**; if it persists, close the console window and relaunch (engine restart) |
| A download looks stuck | Read the strip — **Done ✓ + solid green means finished** |
| "This is a playlist link…" | Open one video and paste **its** link |
| 0 clips found | The video has no speech — use a video with talking |
| A clip stays "TO RENDER", no SEO pack | Restart the engine (close console window, relaunch) — a long-running engine may hold older state |
| "Export locked — Pro clip" while Pro is active | You are in the view-only **demo** project — open your own project |
| Key is rejected | Check the key shape (XXXXXXXX-XXXX-…) and copy the **License key** line from your email |
| "Already active on another PC" | Deactivate on the old PC first |
| The page does not open (127.0.0.1:8791) | The console window was closed — relaunch from the desktop shortcut; do not open two copies at once |
| Setup reports a Python problem | Install **Python 3.13** as well — setup picks it up automatically |

---

*Tip: when something is unclear, read the progress strip first —
Clip2Post always writes down what it did and why.*
