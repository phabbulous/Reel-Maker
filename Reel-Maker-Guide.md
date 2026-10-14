# Reel Maker v4.11: complete guide

Reel Maker is one web page (`index.html`). It crops the bars off your videos, puts the scene on a canvas of your choice (black by default, any colour, or a blurred copy of the video), adds your on-screen text, cuts random clips, and makes MP4 files. Everything runs in your own browser. Your videos are never uploaded, and it costs nothing to run.

---

## 1. What changed in v4 (the saving fix)

Clips were finishing but not reaching your phone or laptop. v4 fixes the saving in these ways:

- **Nothing downloads on its own (v4.3).** Finished clips stay on the page until you tap **Save video**.
- **Save video does the right thing on each device**
  - Computer and Android: a normal download to the Downloads folder (no share menu in the way).
  - iPhone and iPad: the share sheet opens. Choose **Save Video** to put it in Photos, or **Save to Files**.
- **Share** button (Android and computers that support it) sends the clip straight to another app, such as Instagram.
- **Fast engine fallback:** v3 tried to make clips quicker than real time, but if a browser could not do it, the clip simply failed. v4 now switches to the normal recorder automatically. It also uses the normal recorder when the fast engine could only make a clip whose sound would not play on iPhone or Instagram.
- **Multiple videos:** the fast engine in v3 could cut the wrong video when you ticked several. Fixed.
- **If nothing downloads:** the note under the clip says what happened. If the page is open inside another app or page (a preview, a chat window), the browser can block downloads there. Open the page directly in Chrome or Safari. The clip also stays open under **Watch**, where you can press and hold it (or right-click) to save it.

---

### v4.2: the faster engine is now off by default
Clips made by the faster engine (the one in v3) can fail to play on some devices, and I could not verify it in a full browser. v4.2 records at normal speed by default, which is the engine that was tested end to end. A tick box turns the faster engine on if you want to try it. Clips from the faster engine are also checked right after they are made, and if one does not play, the page quietly remakes it with the normal recorder. When a video will not open, the message now says which codecs are inside the file (for example H.264, HEVC, AAC or Opus).

---

## 2. Hosting your own copy (free)

Use the file named exactly `index.html`. Do not rename it.

### GitHub Pages (works fully from an iPhone)
1. Make a free account at github.com and sign in.
2. Create a new repository (the **+** button, then **New repository**). Name it, for example, `reel-maker`, and set it to **Public**.
3. Choose **uploading an existing file** (or **Add file, Upload files**), pick `index.html`, and tap **Commit changes**.
4. Open **Settings, then Pages**. Under **Build and deployment** set **Source** to **Deploy from a branch**, **Branch** to `main`, folder `/ (root)`, and **Save**.
5. After one or two minutes your address appears, like `https://YOUR-USERNAME.github.io/reel-maker/`.
6. On your phone: **Share, Add to Home Screen**.

To update later: **Add file, Upload files**, upload the new `index.html` with the same name and commit.

### Netlify (easiest on a computer)
1. Make a free account at netlify.com.
2. Put `index.html` in a folder.
3. **Add new site, Deploy manually**, and drag the folder in.
4. You get an address like `https://something.netlify.app`. You can rename it in **Site configuration**.

To update later: **Deploys**, drag the folder in again. If you use the quick drop page without an account, the site can be deleted after a short time, so sign in first.

Menu wording changes now and then. Look for the closest label if one is different.

---

## 3. Using Reel Maker

### Step 1: Videos
- **Choose videos**: you can pick several at once. Tick the ones you want clips from. Tap a name to look at that video.
- **Note this moment**: watch the video and tap when a scene starts and again when it ends. The notes can then be turned into clips.

### Step 2: Crop
- Bars (black, white, coloured, caption areas) are found automatically. The dashed box shows what is kept.
- Use **−** and **+** on Top, Bottom, Left and Right, or type a number. **Detect again** repeats the search. Each video has its own crop.
- Detection works for any bar colour. It can miss when the picture is a small part of the frame, when the scene is very dark or plain, when the background is a gradient or pattern, or when text is written on the video itself. Adjust by hand in those cases.

### Step 3: Clips
- **How many**, **Shortest** and **Longest** (seconds): each clip gets its own random length in that range. Empty Longest means up to the whole video. **Exact length** uses the Shortest number for all.
- **Make all clips**: picks the clips (if none exist yet) from every ticked video and makes them one after another.
- **Pick clips only**: picks without making, so you can add text first. Press again for a new random set.
- **Use the full video**: one clip of the whole video.
- **Find busy moments**: scans for movement, scene cuts and loud sound so picks lean toward them. It finds energy, not meaning.
- **Add one at the playhead**: a clip starting where the video is paused.

### Canvas: size, background and video position
Open **Canvas: size, background & video position** under the preview.
- **Aspect ratio:** 9:16, 1:1, 4:5 or 16:9.
- **Background colour:** colour picker, preset swatches, and a full colour strip with a brightness slider. Any colour works.
- **Background type:** solid colour, or **Blurred video** with blur amount (0 to 60, default 40; higher is blurrier) and opacity. In v4.3 the blur is much stronger and smoother than before.
- **Video position:** move the video left, right, up or down with **−** and **+** (or type a number). **Video size** slider from 50% to 200%. **Reset video position** puts it back.

### Text
- Each clip has a text box. **Add another text** gives it more.
- **Text lines for the clips**: paste one line per clip, then **Put the lines on the clips**. **Shuffle** mixes the order.
- Under **Position, size and lines** for each text: choose the **Font** (Inter, Noto Sans Bold, Bebas Neue, Oswald, Oswald Bold, Mukta, Albert Sans, Archivo, Archivo Black, Epilogue, Hind Siliguri, Luckiest Guy, Montserrat Black, Anton), **Place** (above or below the video, top or bottom of the screen, middle), **Size**, **Lines**, and **left/right** and **up/down** with **−** and **+** (hold to repeat) or typed numbers.
- You can drag the preview picture to move the selected text anywhere on the screen. Yellow lines show when it is exactly centred.
- **Use this layout on every clip** copies placement, size and font to the other clips of that video.
- A clip you change after making it is marked, and **Make all clips** remakes only those.

### Preview player
Start and End boxes (v4.7): each has -1s and +1s buttons, and the same on noted moments. Hold to repeat. Start can't pass End, a clip stays at least 1 second long, and the canvas jumps to the new start (or the last moment when you change End).

v4.11: each clip has its own Audio sync box (the Settings box is only the starting value; the Calibrate button measures it on your device). The normal recorder now captures each source frame exactly once and starts on the first moving frame. The fast engine is on by default with automatic fallback, and its sound/picture timing is exact, so Audio sync only affects the normal recorder.

v4.10: every video has a name box; saved clips are named "Name - clip 1.mp4", "Name - clip 2.mp4" and so on (empty = file name; a clip's own File name box wins). Audio sync (ms) sets how far the recorded sound is held back so it matches the picture (default 90; raise it if the sound comes first, lower it if it comes late). The blurred background is cached so recording with blur stays smooth.

v4.9: each clip has ONE Use now button. Change Start and/or End (type it, or use -1s/+1s), then press Use now: the clip takes those times and the canvas jumps to its start. Press Make clip to build the video again. Set start here and Set end here copy the time of the player you used last. Duplicate copies a clip right below itself. Each finished clip has a File name box. Your background, blur, aspect ratio and clip counts and lengths are remembered on this device. Older note, v4.8: the Use now buttons, Note this moment and add clip here take the time from whichever player you used last (source video, preview bar, or Show this clip). After Use now the canvas jumps to the clip's new start or end.

Under the preview: play or pause, mute, seek bar, and speed (0.5x to 2x). The play button previews the selected clip and stops at its end. The source video at the top plays freely, past any clip. Since v4.6 the source video, the canvas preview and the per-clip "Show this clip" player are three separate players: the canvas stops at the clip's end and replays from its start, changing a clip's start or end moves the canvas to the new start, starting one player pauses the others, and text edits redraw the preview even after a clip has ended.

### Saving
- Clips stay on the page after they are made. Tap **Save video** on each one. On a computer or Android it downloads. On iPhone it opens the share sheet: choose **Save Video** to put it in Photos.
- **Watch** plays the clip so you can check it.

---

## 3b. Best way to use Reel Maker on an iPhone

1. **Host it once** (GitHub Pages, section 2) and open the address in **Safari**. Do not open it inside another app or a chat preview, because downloads and recording can be blocked there.
2. **Add to Home Screen:** Share, then Add to Home Screen. It opens like an app.
3. **Choose videos** from your Photo Library. iPhone videos (including HEVC) play fine in Safari.
4. **Turn off sleep while you work:** Settings, Display & Brightness, Auto-Lock, Never. Turn it back on afterwards. Also turn off Low Power Mode, which can slow recording.
5. **Stay on the page:** do not switch apps or lock the phone while clips are being made. Recording runs at normal speed (a 20-second clip takes about 20 seconds).
6. **Make 4 to 6 clips per batch.** More uses a lot of phone memory.
7. **Save each clip right away:** tap **Save video**, then **Save Video** in the share sheet. It goes to Photos. (Save to Files is the other choice.)
8. **Keep it light:** 1080p source videos work best. Very long or 4K videos are slow and heavy on a phone.
9. **Do a 2-clip test first** before a big batch.
10. If a big job is needed, do the picking and text on your phone and the heavy recording on a laptop.

---

## 4. Advice

**Campaign workflow**
1. Load the video and check the crop.
2. Set How many, Shortest and Longest, then **Pick clips only**.
3. Paste your hype lines and **Put the lines on the clips**.
4. Check two or three clips, adjust one clip's text layout, then **Use this layout on every clip**.
5. **Make all clips**.

**Phone tips**
- Make 4 to 6 clips per batch. Keep the screen on and the tab open while clips are being made.
- On iPhone, save each clip right after it finishes.
- Keep text short. Two lines at the default size fit best.

**If clips do not appear in your Gallery on Android:** open the Files app, then Downloads. Move them to Movies or DCIM if you want them in the Gallery.

**Fonts:** they load from Google Fonts, so you need internet the first time.

---

## 4b. Check this browser (v4.5)

If the tool works in one browser but not another, open **Check this browser** at the top of the page and tap **Run the check**. It lists, for the browser you are in: whether it plays H.264 and HEVC video, whether it can record, whether the page is open inside another app (which can block downloads), whether the share sheet exists, and more. Run it in both browsers and compare. Anything marked NO is what that browser cannot do.

Common fixes:
- **Cannot play H.264 or the picture is missing:** use the current Chrome, Edge or Safari. Open the page directly, not inside another app.
- **Downloads blocked:** allow downloads for the site in the browser's settings, and allow multiple downloads if asked.
- **Open inside another app or preview:** open the address in Chrome or Safari instead.
- **Browser very old:** update it.

---

## 5. Troubleshooting

| Problem | What to try |
|---|---|
| Save did nothing | Read the line under the clip. If the page is open inside another app, open it directly in Chrome or Safari. Or use Watch, then press and hold the video. |
| iPhone: no download | Normal. Tap Save video, then Save Video in the share sheet. |
| Several downloads blocked on computer | Allow multiple downloads for the site when the browser asks. |
| Video will not open | v4.1 now says why, with the file name, type and size. Sound but no picture usually means an iPhone HEVC video opened in Chrome or Edge: use Safari, or export as Most Compatible (H.264). "Took too long" means a very large file: try a shorter copy. Do not choose a clip the tool made earlier on an iPhone if it has Opus sound: remake it. |
| Crop too loose or tight | Use the Top, Bottom, Left, Right buttons, or Detect again. |
| Recording fails or freezes | Make fewer clips at once, close other apps, keep the screen on. |
| Text too big or cut off | Lower Size, or set Lines to 2 or 3. |
| Page looks old after updating | Refresh, or clear the site's cache. |

---

## 6. Privacy and limits

- Videos, clips and text stay on your device. The only outside requests are for the fonts and the page itself.
- Making clips can be real time (a 20-second clip takes about 20 seconds) when the fast engine is not available.
- Very large videos can be slow or run out of memory on a phone.
- Tested here: desktop Chrome (download, auto-download, share, iPhone-style save path, colour and position controls). Not tested here: real iPhone Safari and real Android Chrome. The iPhone default sound sync is a guess until you tap Calibrate. Do a two-clip test first.
