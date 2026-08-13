# Troubleshooting and gotchas

The stuff you might actually run into, and what to do about it.

## Install

**"Windows protected your PC" (SmartScreen).**
The app is not code-signed, so Windows is cautious with it. Click **More info**, then **Run anyway**. This is expected for small unsigned apps.

**Antivirus flags the exe.**
PyInstaller-packaged apps occasionally trip false positives. The download only comes from this page; if your AV quarantines it, add an exception or restore it.

**First launch takes a while.**
It is downloading FFmpeg (about 80 MB) and yt-dlp in the background. The status bar shows progress. This only happens once.

## Downloads

**Error mentioning yt-dlp being out of date (for example "older than 90 days").**
An old yt-dlp eventually cannot talk to YouTube at all. The app refreshes yt-dlp automatically on launch; if you see this error, close the app and open it again so the updater can do its pass. If it somehow persists, delete the folder `%LOCALAPPDATA%\yt-dlp` and relaunch: the app downloads a fresh copy by itself.

**Downloads suddenly failing (403 errors, "unable to extract" and similar).**
Nine times out of ten this is YouTube changing something and an outdated yt-dlp. Relaunch the app so it can update its tools, then try again.

**Downloaded file is not in the save folder.**
If your save folder is iTunes' "Automatically Add to iTunes" folder, iTunes grabs the file within seconds and moves it into its own library structure. That is iTunes working as designed. The History popup shows what was downloaded and when.

## Playlists

**I pasted a playlist link but only got one video.**
Two possibilities: the playlist popup is off (enable "Ask about playlists" in Settings, gear icon top right), or the link was an auto-generated YouTube Mix, which the app ignores by default so Mix-flavored links behave like single videos. Real user-made playlists still prompt when asking is enabled.

**Turbo with a playlist link downloads the whole playlist.**
That is intentional when playlist asking is enabled, and the app warns you first. With asking disabled, Turbo grabs just the one video.

## Metadata

**iTunes picked the wrong song or album.**
Click "Wrong match?" above the metadata fields. You can edit the search text, filter by artist, album, or year, pull a whole album tracklist, or paste an Apple Music link directly for songs missing from the store search.

**A song genuinely is not on iTunes.**
Switch Source to YouTube to tag from the video info instead, or override any field by checking the box next to it and typing your own.

## Updates

**The app seems to update every time it starts.**
It should not: there is a built-in cooldown that prevents update loops. If you ever see back-to-back updates, that is usually two releases shipping close together, not a loop. Make sure only one copy of the app is running.

**I want to check my version.**
The current version shows in the update messages in the status bar on launch.
