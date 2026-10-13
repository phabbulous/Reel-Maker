# Reel Maker

Turn any video into 9:16 reels in your browser. Reel Maker crops off the bars and burned-in captions, centres the scene on a canvas you choose, adds your own on-screen text, cuts random clips, and gives you MP4 files. Everything runs on your device. Your videos are never uploaded.

Version 4.10 · one file: `index.html` · no install, no account, free.

---

## Quick start

1. Open `index.html` in Chrome, Edge or Safari (host it first: see "Put it online" below).
2. Tap **Choose videos** and pick one or more.
3. Check the crop (it is found automatically; adjust with the − and + buttons if needed).
4. Set **How many**, **Shortest** and **Longest** (seconds), and optionally paste text lines.
5. Tap **Make all clips**.
6. Tap **Save video** on each finished clip.

---

## What it does

- **Auto crop:** finds and removes black, white, coloured and caption bars. Adjust Top, Bottom, Left and Right with − and + or typed numbers.
- **Random clips:** a set number of clips from each video, each with its own random length, starting at random places and allowed to overlap. Or a full-length clip with no cutting, or an exact length.
- **Busy moments finder:** optional scan for movement, scene cuts and loud sound so clips lean toward the action. It finds energy, not meaning.
- **Several videos at once:** tick the ones you want clips from. Each keeps its own crop and clips.
- **Notes:** tap while watching to mark where a scene starts and ends, then turn the notes into clips.
- **Text:** several texts per clip, 14 fonts (Inter, Noto Sans Bold, Bebas Neue, Oswald, Oswald Bold, Mukta, Albert Sans, Archivo, Archivo Black, Epilogue, Hind Siliguri, Luckiest Guy, Montserrat Black, Anton). Place it above or below the video, at the top or bottom of the screen, or in the middle. Set size and lines, and move it with − and + or by dragging the preview.
- **Text lines:** paste one line per clip and apply them all at once, shuffled if you like.
- **Canvas:** 9:16, 1:1, 4:5 or 16:9. Any background colour (picker, swatches, full palette), or a blurred copy of the video. Move and resize the video on the canvas.
- **Start and End nudge buttons (v4.7):** next to every Start and End box (and on noted moments) are -1s and +1s buttons. Hold one to keep stepping. Start can't pass End, and a clip stays at least 1 second long.
- **Use now (v4.9):** one Use now button per clip. Change Start and/or End (type, or use -1s/+1s), press Use now, and that clip takes those times. Then press Make clip to build the video again. "Set start here" and "Set end here" copy the time of the player you used last.
- **Video names (v4.10):** each video in the list has a name box. Saved clips are named "Your name - clip 1.mp4", "- clip 2" and so on. Leave it empty to use the file name. A clip's own File name box still wins for that clip.
- **Sound sync and smoother blur (v4.10):** the sound used to land about 0.09 s before the picture in made clips. It is now held back to match. If it is still off on your device, change "Audio sync (ms)": raise it if the sound comes first, lower it if the sound comes late. The blurred background is also much lighter to record, so clips with blur are smoother.
- **More in v4.9:** Duplicate clip, a File name box on each finished clip, and remembered settings (background, blur, aspect ratio, clip counts and lengths).
- **Older note (v4.8):** Use now, Note this moment and add clip here take the time from the player you used last: the source video, the preview bar under the canvas, or a clip's Show this clip player.
- **Preview player:** play, mute, seek, and 0.5x to 2x speed. The play button previews the selected clip and stops at its end. The source video above always plays freely, past any clip. The two are fully separate (v4.6): playing one pauses the other, and changing a clip's start or end jumps the preview to the new start without touching the source video. Text edits redraw the preview, also after a clip has finished.

---

## Saving

Finished clips stay on the page until you tap **Save video**. Nothing downloads on its own.

| Device | What Save video does |
|---|---|
| Computer, Android | Normal download to your Downloads folder |
| iPhone, iPad | Opens the share sheet: choose **Save Video** (Photos) or **Save to Files** |

A **Share** button also appears on Android and computers that support it. **Watch** plays the finished clip.

---

## Put it online (free)

Use the file named exactly `index.html`.

**GitHub Pages (works from an iPhone)**
1. Make a free account at github.com.
2. Create a new **Public** repository, for example `reel-maker`.
3. **Add file, Upload files**, choose `index.html`, **Commit changes**.
4. **Settings, Pages**: Source = Deploy from a branch, Branch = `main`, folder = `/ (root)`, Save.
5. After a minute or two the address appears: `https://YOUR-USERNAME.github.io/reel-maker/`.
6. On a phone: Share, **Add to Home Screen**.

To update, upload the new `index.html` with the same name.

**Netlify:** make a free account, put `index.html` in a folder, then **Add new site, Deploy manually** and drag the folder in. Sign in first, because anonymous drops can be deleted after a short time.

---

## Best way to use it on an iPhone

1. Open the hosted address in **Safari** (not inside another app or a chat preview).
2. Add it to the Home Screen.
3. Turn off Auto-Lock and Low Power Mode while you work.
4. Stay on the page while clips are made. Recording runs at normal speed (a 20-second clip takes about 20 seconds).
5. Make 4 to 6 clips per batch.
6. Tap **Save video**, then **Save Video**, right after each clip finishes.
7. Use 1080p source videos. Do a 2-clip test before a big batch.

---

## Troubleshooting

| Problem | What to try |
|---|---|
| Works in one browser, not another | Open **Check this browser** at the top and run the check in both. Anything marked NO is what that browser cannot do. |
| "Cannot play that video" | The message names the codecs inside the file. HEVC from an iPhone needs Safari, or export as Most Compatible (H.264). |
| Save did nothing | If the page is open inside another app, open it directly in Chrome or Safari. Or use Watch, then press and hold (or right-click) the video. |
| Several downloads blocked | Allow multiple downloads for the site when the browser asks. |
| Crop too loose or tight | Use the crop − and + buttons, or **Detect again**. Detection can miss when the picture is a small part of the frame, the scene is very dark, or the background is a gradient. |
| Recording fails or freezes | Fewer clips at a time, close other apps, keep the screen on. |
| Text too big or cut off | Lower Size, or set Lines to 2 or 3. |
| Fonts look wrong | Fonts load from Google Fonts and need internet the first time. |
| Page looks old after an update | Refresh, or clear the site's cache. |

**Faster engine (experimental):** an optional tick box makes clips quicker than real time. It is off by default because its files may not play on every device. Each clip it makes is test-played, and if it fails the page remakes it with the normal recorder.

---

## Privacy

Videos, clips and text stay on your device. The only outside requests are the fonts (Google Fonts) and the page itself from your host.

---

## Limits

- Making clips normally runs in real time.
- Very large or 4K videos can be slow or run out of memory on a phone.
- The busy-moments finder cannot understand what is happening in a scene.
- Tested in desktop Chrome. Not tested on real iPhone Safari, real Android Chrome, or the faster engine in a full browser, so run a short test first.

---

Phabb Made It
