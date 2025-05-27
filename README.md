# scrubnuc

**scrubnuc** is a nuclear-grade Bash script for Linux that removes all metadata from `.png` and `.jpg` image files using open-source tools. It was created with privacy, control, and clean output in mind, especially for Linux users who want a no-nonsense command-line solution.

---

## 🚀 Features

- ✅ Supports `.jpg`, `.jpeg`, and `.png` files
- 🔁 Automatically converts `.jpg` files to `.png`
- 🧼 Removes EXIF, tEXt, timestamps, software tags, and more
- 💾 Preserves original files in `~/scrubnuc_backups`
- 📝 Logs each run to `~/scrubstrong_logs/` with timestamped logs
- 🔊 Plays a GNOME notification chime upon completion
- 🐧 Runs fully offline and fast from the command line

---

## 🛠️ Requirements & Installation

Install the required packages:

```bash
sudo apt install mat2 imagemagick pngcrush
```
Then install `scrubnuc` system-wide:
```bash
cd ~/Downloads
sudo cp scrubnuc /usr/local/bin/
sudo chmod +x /usr/local/bin/scrubnuc
```
You can now run `scrubnuc` from any terminal.

---

## 📦 Usage

From the directory containing your image files:
```bash
scrubnuc image1.jpg image2.png image3.jpg
```
Each file will be:

- Cleaned in-place using mat2

- Re-encoded via convert

- Fully sanitized using pngcrush (for PNG files)

- Output as:
    `image_fullyscrubbed.png`
  or
    `image_converted_fullyscrubbed.png` (if originally a .jpg)

Originals will be moved to `~/scrubnuc_backups`, and a detailed log is saved under `~/scrubstrong_logs/`.

---

## 🔐 Why?

Images contain metadata that can reveal:

- Device info

- Location data

- Timestamps

- Editing software history

**scrubnuc** is built for creators, professionals, and privacy-conscious users who want to share media, not data.

---

## 📁 Example Output

If you run

```bash
scrubnuc my_photo.jpg
```
You’ll get:

- `my_photo_converted_fullyscrubbed.png` in your folder

- `my_photo.jpg` moved to `~/scrubnuc_backups/`

- Entry logged in `~/scrubstrong_logs/scrubnuc_YYYY-MM-DD.log`

---

## ✅ License

[MIT License](https://opensource.org/licenses/MIT)

> Use it. Improve it. Break metadata, not your flow.

---

## 🔔 Optional: Sound Notification

This script uses `paplay` to play a GNOME desktop notification sound when finished.  
If you're not hearing anything at the end of the scrub, install this package:

```bash
sudo apt install libcanberra-gtk3-module
```
Or comment out the `paplay` line at the bottom of the script if you prefer silence. 🙂

---

## 🧠 Author

**Tolga Yenici**

Mechanical Engineer • GNU/Linux Enthusiast • Privacy Advocate

https://github.com/tolgayenici

---
