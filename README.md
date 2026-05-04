AlarmLoop 🔁⏰

A lightweight Progressive Web App alarm that plays a tone and vibrates repeatedly at a custom interval – built for Android, works entirely in the browser.

---

Features

· ✅ Set any repeat interval – seconds or minutes
· 🔊 Tone alarm – plays a clear beep using the Web Audio API (no audio file needed)
· 📳 Vibration pattern – triggers a strong, repeating vibration (Android)
· 🖥️ Keeps screen awake – uses the Wake Lock API so the alarm keeps running with the screen on
· 📲 Installable PWA – add to your home screen and use like a native app
· 🧩 Single‑page, zero dependencies – just one HTML file
· 🎛️ Start/Stop controls – instant alarm with a single tap (user gesture required)

---

Quick Start

1. Download index.html from this repository.
2. Open it in Chrome on Android (no server needed for basic use).
3. Set your interval, tap Start Alarm.
4. Keep the screen on or allow the Wake Lock prompt.

For the full PWA experience (installable, works offline):
Serve the folder via HTTPS (e.g., npx serve) and add the supplied manifest.json + a simple service worker.

---

How It Works

· A setInterval triggers the alarm every x seconds (or minutes).
· The alarm action:
  · Creates an oscillator via the Web Audio API → 0.4 s square‑wave beep
  · Calls navigator.vibrate([200,100,200,100,200]) for a distinctive vibration pattern
· navigator.wakeLock.request('screen') prevents the display from sleeping.
· A user gesture (button tap) is required to start the audio context and vibration – Android browsers block auto‑play.

---

Installation (PWA)

1. Serve the project over HTTPS.
2. Open the page in Chrome on Android.
3. Tap the “Add to Home screen” prompt (or use the menu).
4. The app will appear as a standalone icon on your launcher.

---

Future Roadmap

Milestone Description
🧠 Custom tones Choose frequency / duration / waveform (beep, siren, chime)
🌙 Dark mode Automatic theme based on system preference
🔔 Background alarms Service Worker + Notifications to ping you even when the tab is closed
⏸️ Snooze / Pause Temporary halt without resetting the interval
💾 Persistent settings Remember interval and preferences with localStorage
🎚️ Volume control Independent volume slider for the alarm
📋 Alarm history Log of triggered alarm times
🌍 Internationalisation Multi‑language support
📎 Share configuration Generate a URL with pre‑set interval
🔊 Gradual volume ramp Softer start that gets louder over repeats

---

Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you’d like to change.

This project is intentionally minimal, so enhancements should keep dependencies at zero.

---

License

MIT – free for personal and commercial use.

---

Enjoy a truly reliable repeating alarm right from your browser!
Questions or ideas? Open an issue. 📬
