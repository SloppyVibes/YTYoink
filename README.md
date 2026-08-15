<p align="center"><img src="assets/shot_main.png" alt="YTYoink main window" width="560"></p>

# YTYoink

<p align="center">
<img alt="100% AI coded" src="https://img.shields.io/badge/100%25-AI_coded-7c5cff?style=for-the-badge">
<img alt="Windows" src="https://img.shields.io/badge/platform-Windows-2ea44f?style=for-the-badge">
</p>

**Every line of this app was written by AI**, with a human directing, testing, and approving each release. That goes for all SloppyVibes projects: 100% AI coded, human steered.

YTYoink is a YouTube audio downloader for Windows that takes the metadata as seriously as the download. Most downloaders hand you a file named after the video. YTYoink hands you a finished song: real title, artist, album, year, and genre matched from the iTunes catalog, with proper cover art embedded, ready to drop straight into iTunes, your phone, or any music player.

## Downloading

- **Paste a link and hit Fetch Info**, or hit **SearchYT** and find the song without leaving the app: 100 results with thumbnails and view counts, length filters, and a live search box to narrow by title or channel.
- **Whole playlists.** Paste a playlist link and get a checklist of every video: tick exactly the ones you want, search within the playlist, shift-click to select ranges, and choose between downloading the batch in one go or reviewing each song's metadata one by one. Auto-generated YouTube Mixes are ignored by default, so a link copied out of a Mix grabs just that one video instead of surprising you with fifty.
- **Your format.** M4A by default (the iTunes and iPhone sweet spot), MP3, or Opus, which keeps YouTube's original audio untouched with no re-encode. Cover art is embedded in every format, Opus included.
- **Turbo mode** skips the metadata stage entirely when raw speed is all you need.

## Metadata that actually gets it right

- Every fetch is matched against the **iTunes catalog**, so songs arrive with the same title, artist, album, year, and genre they have in the store, not whatever the video uploader typed.
- **Wrong match? One click fixes it.** Edit the search, narrow it by artist, album, or year, pull up a full album tracklist and pick the exact track, or paste an Apple Music link for songs the store search cannot find. Batch downloads even remember your album pick for the rest of the playlist.
- Prefer the video's own info? Flip the source to **YouTube**. Want full control? Tick any field and type your own value.

## Artwork done properly

- Pick your cover per song: the **iTunes artwork**, the **YouTube thumbnail**, or **your own image**, browsed, pasted with Ctrl+V, or dragged straight into the window.
- Your own pictures are **automatically cropped and sized to standard cover-art resolution**, so they display pixel-perfect in iTunes, on your phone, and in every music app, no editing required.
- Hover any artwork tile for an enlarged preview before you commit.

## Quality of life

- **Download history** remembers everything, and an amber **!** badge warns you before you download a song you already have, with the date on hover.
- **Zero maintenance.** The app updates itself on launch and keeps its own tooling (yt-dlp, FFmpeg) current, so it does not quietly rot like most downloaders do.

<p align="center">
<img src="assets/shot_search.png" alt="SearchYT popup" width="460">
&nbsp;&nbsp;
<img src="assets/shot_fetched.png" alt="Fetched video with iTunes metadata and artwork choices" width="460">
</p>

## Installation

1. Download **YTYoink_setup.exe** from the [latest release](../../releases/latest). Ignore the other files on the release page (`YTYoink.exe`, `YTYoink_full.zip`): those are downloaded automatically by the installer and the auto-updater, never by you.
2. Run it. Windows SmartScreen may warn you because the app is not code-signed (certificates cost money and this is a small personal project). Click **More info**, then **Run anyway**.
3. Approve the administrator prompt. The app installs to Program Files.
4. The setup then does everything on its own, and tells you what it is doing at each step:
   - downloads the full app package (about 36 MB) from this page
   - installs it and creates Start Menu and Desktop shortcuts
   - launches the app
5. On first launch the app checks its dependencies and **installs anything missing automatically**: yt-dlp and FFmpeg, via winget when available or direct official downloads otherwise (FFmpeg is about 80 MB, so the very first launch can take a couple of minutes). Progress shows in the status bar at the bottom. When it says **Ready.** you are good to go.

Nothing else to configure. Pick a save folder once (pointing it at iTunes' "Automatically Add to iTunes" folder is a popular choice) and start yoinking.

## How to use

The everyday flow is three clicks:

1. **Paste a YouTube link** in the URL box (or hit **SearchYT** and find the song by name, then click a result). Even easier: copy a YouTube link anywhere, then just click the empty URL box, and the link **pastes itself and starts fetching automatically**. It never overwrites something already typed in the box.
   - One exception: for the first moments after launch, while the status bar still says it is checking dependencies, fetching waits. If you jump in that fast, the app tells you it is still checking; once the status bar says **Ready.**, click **Fetch Info** and carry on.
2. **Hit Fetch Info.** The app pulls the video, matches the song on iTunes, and fills in title, artist, album, year, genre, and artwork. Look it over:
   - Wrong song or album? Click **Wrong match?** and pick the right one, or refine the search with artist, album, and year filters:

   <p align="center"><img src="assets/shot_match.png" alt="Choose iTunes match popup with search, filters, and candidate list" width="620"></p>

   - Want different cover art? Click one of the artwork tiles: **iTunes**, **YouTube**, **Custom** (browse, Ctrl+V paste, or drag an image in), or **None**. Hover a tile to see it enlarged.
   - Want to change a field by hand? Tick the checkbox next to it and type your own value.
3. **Hit Download.** The tagged audio file lands in your Save to folder. Done.

Worth knowing:

- An orange **!** next to the video title means you already downloaded this one before. Hover it to see when.
- **Turbo** (top right) skips all the metadata work and just grabs the audio as fast as possible.
- **History** shows everything you have downloaded, newest first.
- The **gear icon** opens settings: output format (M4A, MP3, Opus), preferred metadata and artwork source, and playlist behavior.
- Pasting a playlist link (with playlist asking enabled in settings) pops a checklist so you pick exactly which videos to grab, with a search box and a review-each-one mode for per-song metadata control.

## Updates

YTYoink keeps itself current. Every launch it checks this page for a new version, shows a small progress window if one is found, and relaunches itself updated. It also keeps yt-dlp fresh automatically, which matters because YouTube changes constantly and stale downloaders break.

## Built on the shoulders of giants

YTYoink is glue around some excellent open source software and public services. Credit where credit is due:

| Project | Role | License |
|---|---|---|
| [yt-dlp](https://github.com/yt-dlp/yt-dlp) | video/audio downloading | Unlicense |
| [FFmpeg](https://ffmpeg.org/) (builds by [gyan.dev](https://www.gyan.dev/ffmpeg/builds/)) | audio conversion and tagging | GPL |
| [mutagen](https://github.com/quodlibet/mutagen) | Opus cover art embedding | GPL-2.0 |
| [Pillow](https://python-pillow.org/) | artwork processing and the rounded UI | MIT-CMU |
| [Requests](https://requests.readthedocs.io/) + [certifi](https://github.com/certifi/python-certifi) | HTTPS everywhere | Apache-2.0 / MPL-2.0 |
| [PyInstaller](https://pyinstaller.org/) | packaging | GPL with exception |
| [iTunes Search API](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/iTuneSearchAPI/) | song metadata and artwork | Apple public API |
| [Poppins](https://fonts.google.com/specimen/Poppins) and [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue) | bundled fonts | SIL OFL 1.1 |

## Safety and verification

We take the "random exe from the internet" problem seriously. What you can check:

- **SHA-256 checksums** are published in every release's notes. After downloading, run `certutil -hashfile YTYoink_setup.exe SHA256` in a terminal and compare: a match proves your file is byte-for-byte the one we built and uploaded.
- **Every release is scanned on VirusTotal.** Each build is uploaded to [VirusTotal](https://www.virustotal.com) at release time and checked against ~70 antivirus engines; the scan report links are in every release's notes. You are welcome to re-upload and verify yourself.
<!-- VT:START -->
**Latest release scan results (v1.1.48):**

| File | Result | Report |
|---|---|---|
| YTYoink_setup.exe | 72 of 75 engines clean | [view scan](https://www.virustotal.com/gui/file/af7a6caf16033ba616d517f5222b3cf03f5bcf082c774ad5d1fac20cfca33e5c) |
| YTYoink.exe | 71 of 75 engines clean | [view scan](https://www.virustotal.com/gui/file/d7664402ac0c8a85425399a36a303e9ad61ef935bc284379e209fe884bb1bb1a) |
| YTYoink_full.zip | 75 of 75 engines clean | [view scan](https://www.virustotal.com/gui/file/7db779dfb88613e01cb6ab15c1af1c36568dbcddac3b3f5eba181af658a3e253) |
<!-- VT:END -->

- **About the few detections you may see there:** a handful of machine-learning heuristic engines (and occasionally Defender's cloud model, as generic "Wacatac!ml") flag unsigned Python-packaged apps on pattern alone. It is a well-documented false-positive class: the overwhelming majority of engines, including Kaspersky, BitDefender, ESET, Avast, Sophos, and Malwarebytes, rate every release clean. We file false-positive reports with vendors that misflag.
- **One source of truth.** The only official download location is this repository's Releases page, and the app only ever updates itself from here over HTTPS. If you got YTYoink anywhere else, do not run it.
- **Why SmartScreen still warns:** the app is not code-signed (publisher certificates are an ongoing cost that does not make sense for a small free tool yet). SmartScreen flags unsigned software by default regardless of its behavior. The checksums and scans above are the compensating transparency.

## Notes

- This repository hosts releases only. There is no source code here.
- Something acting up? See [TROUBLESHOOTING.md](TROUBLESHOOTING.md).
- YTYoink is a personal-use tool. Respect YouTube's Terms of Service and only download content you have the rights to.
