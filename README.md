# 🔊 Whine Finder

A phone web app that uses your microphone to track down a faint, high-pitched electrical whine (coil whine, chargers, transformers, LED drivers, monitors…).

**Live app:** https://cyreb7.github.io/whine-finder/

## How it works

- Captures the mic with echo cancellation, noise suppression and auto-gain **off** (those features remove exactly the kind of steady tone you're hunting).
- Runs a high-resolution FFT (16384 points, ~3 Hz bins) and keeps a slow running average so steady tones stand out while speech and transient sounds fade.
- Finds narrow peaks that sit well above the local noise floor and lists them as candidate whines. It auto-picks the strongest, or you can tap one to lock it.
- Shows the locked tone's level as a big hot/cold meter with a "warmer/colder" trend, a 25-second history, and a loudest-seen marker, so you can sweep the room and home in.
- Lets you save readings at each suspect device to compare them side by side.

Everything runs locally in the browser. No audio is recorded or uploaded.

## Use

Open the link on your phone, tap **Start listening**, allow the microphone, and walk slowly around with the phone's bottom edge (where the mic is) pointed at suspects.

It's a single static `index.html` with no build step or dependencies.
