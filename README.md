# Raspberry Pi Related
## Taking screenshot (Select Area)
Usually I use Flameshot but at this point of time it is not yet supported in wayland. Therfore we are going to edit the `~/.config/wayfire.ini` and add below
```
binding_screenshot_interactive = <shift> KEY_SYSRQ
command_screenshot_interactive = slurp | grim -g -
```

---
## Download Unlisted Video From Youtube using cookies
1. Get Chanel ID in Youtube URL (eg : UCMG9SzMN1ydBSkyTxCaueOQ -> Change to U**U**MG9SzMN1ydBSkyTxCaueOQ)
2. To check if I am using Chrome or Chromium `chromium-browser --version || google-chrome --version
3. install `yt-dlp` using pip. Need to create venv
4. Download using below command
```bash
yt-dlp -f "bv*+ba/best" \
  --merge-output-format mp4 \
  --cookies-from-browser chromium \
  --download-archive downloaded.txt \
  -o "%(title)s.%(ext)s" \
  "https://www.youtube.com/playlist?list=UUMG9SzMN1ydBSkyTxCaueOQ"
```
### 🔍 Explanation:

* `--download-archive downloaded.txt`: yt-dlp keeps track of downloaded video IDs in this file.
* If a video is already in the archive file, it **will be skipped**.
* `downloaded.txt` is a plain text file created/updated automatically by yt-dlp.
* Keep `downloaded.txt` in the same directory as your script or working folder.
* If you delete this file, yt-dlp will re-download everything again.

  ---
