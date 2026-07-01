Markdown
# my-useful-scripts

A curated collection of professional terminal snippets, automation scripts, and command-line tricks to speed up daily workflows. Built for quick reference across different environments.

👤 **Author:** [@AliHamza-Coder](https://github.com/AliHamza-Coder)  
🚀 **Maintained by:** Ali Hamza  

---
# IDM-Reset-by-single-command


reg delete "HKEY_CURRENT_USER\SOFTWARE\Classes\WOW6432Node\CLSID\{07999AC3-058B-40BF-984F-69EB1E554CA7}" /f


## 📽️ Video Compression Scripts
These commands scan the current directory for all `.mp4` files, create a new folder named `compressed_videos`, and batch-compress them using FFmpeg (H.264 encoding with CRF 23). This guarantees a massive reduction in file size with virtually no noticeable loss in visual quality.

### 🔷 PowerShell (Windows)
```powershell
New-Item -ItemType Directory -Force -Path "compressed_videos"; Get-ChildItem *.mp4 | ForEach-Object { ffmpeg -i $_.FullName -c:v libx264 -crf 23 -preset medium -c:a copy "compressed_videos\$($_.Name)" }
⬛ Command Prompt / CMD (Windows)
DOS
mkdir compressed_videos && for %i in (*.mp4) do ffmpeg -i "%i" -c:v libx264 -crf 23 -preset medium -c:a copy "compressed_videos\%i"
🐧 Bash Terminal (Linux / macOS)
Bash
mkdir -p compressed_videos && for i in *.mp4; do ffmpeg -i "$i" -c:v libx264 -crf 23 -preset medium -c:a copy "compressed_videos/$i"; done
🖼️ Image Optimization Scripts
These commands target all .jpg, .jpeg, and .png images in the current directory, generate a new folder named compressed_images, and optimize them.

💡 Quality Control: These scripts use -q:v 5 (FFmpeg quality scale 1-31, where lower is better). Level 5 provides an optimal balance, dropping file size significantly while retaining crisp details.

🔷 PowerShell (Windows)
PowerShell
New-Item -ItemType Directory -Force -Path "compressed_images"; Get-ChildItem *.jpg, *.jpeg, *.png | ForEach-Object { ffmpeg -i $_.FullName -q:v 5 "compressed_images\$($_.Name)" }
⬛ Command Prompt / CMD (Windows)
DOS
mkdir compressed_images && for %i in (*.jpg *.jpeg *.png) do ffmpeg -i "%i" -q:v 5 "compressed_images\%i"
🐧 Bash Terminal (Linux / macOS)
Bash
mkdir -p compressed_images && for i in *.jpg *.jpeg *.png; do ffmpeg -i "$i" -q:v 5 "compressed_images/$i"; done
⚙️ Prerequisites
To execute these commands successfully, ensure that FFmpeg is installed on your operating system and added to your system's Environment Variables (PATH).

Windows: Install via Winget: winget install Gyan.FFmpeg

macOS: Install via Homebrew: brew install ffmpeg

Linux: Install via APT: sudo apt install ffmpeg

📑 Feel free to star ⭐ this repository if you find these snippets helpful!
