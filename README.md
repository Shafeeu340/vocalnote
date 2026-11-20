# VocalNote — Obsidian Pro Notepad & Natural TTS

A professional Progressive Web App (PWA) for writing notes in a distraction-free dark workspace and listening to them with natural human-like text-to-speech voices.

## Features

- Clean Obsidian Dark / Pure OLED Black themes
- Multiple notes with search, auto-save, and local storage
- Natural TTS with voice selection, speed, and pitch controls
- Highlight text to listen to a selection
- Fully installable as a PWA on Android, iOS, and desktop
- Offline support via service worker
- Multiple icon sizes for all devices (including maskable icons for Android)

## File Structure

```
vocalnote-pwa/
├── index.html          # Main app
├── manifest.json       # PWA manifest
├── sw.js               # Service worker (offline caching)
├── favicon.ico
├── favicon-32x32.png
└── icons/              # All device icons
    ├── icon-72x72.png
    ├── icon-96x96.png
    ├── ... (up to 1024)
    ├── icon-maskable-192x192.png
    ├── icon-maskable-512x512.png
    └── apple-touch-icon.png
```

## How to Deploy on GitHub

1. Create a new public repository on GitHub (e.g. `vocalnote`).
2. Upload the entire `vocalnote-pwa` folder contents (or the folder itself) to the repository root.
3. Go to **Settings → Pages**.
4. Under "Build and deployment", select **Deploy from a branch**.
5. Choose `main` (or `master`) branch and `/ (root)` folder.
6. Save. Your app will be live at `https://yourusername.github.io/vocalnote/`.

Once live over HTTPS, users can install it:

- **Android (Chrome)**: Menu → "Add to Home screen" or "Install app"
- **iOS (Safari)**: Share → "Add to Home Screen"
- **Desktop**: Install icon in the address bar

## Local Testing

Serve the folder with any static server:

```bash
npx serve .
# or
python -m http.server 8000
```

Then open `http://localhost:8000` and use Chrome DevTools → Application → Manifest / Service Workers to verify.

## Notes

- All notes are stored locally in the browser (localStorage). They stay private and offline.
- TTS uses the browser's built-in Speech Synthesis API with the best available natural/neural voices.
- Theme preference and voice settings are also saved locally.
