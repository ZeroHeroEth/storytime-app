# 🌙 Storytime

An AI-powered interactive bedtime story app built for toddlers. Pick a hero, pick an adventure, and listen to a personalized story read aloud by a professional AI narrator — with each word highlighted as it's spoken.

**[▶️ Try it live](https://zeroheroeth.github.io/storytime-app)**

---

## Features

- 🦁 **16 characters** × 🏖️ **16 settings** = 256 unique stories
- 🎙️ **4 AI narrator voices** matched to the story setting
- ✨ **Word-by-word highlighting** synced to audio in real time
- ⏸️ **Play, pause, resume** from exactly where you left off
- 📱 **PWA** — installable on iPad as a home screen app, works offline
- 🌐 **No login required** — open and play instantly

---

## Narrator Voices

| Group | Settings | Voice |
|---|---|---|
| Wild & Natural | Beach, Mountains, Volcano, Forest, Desert | Imogen |
| Magical & Cosmic | Night Sky, Space, Rainbow, Mushroom Kingdom | Christopher |
| Human & Built Worlds | Japan, City, Castle, Egypt | Edward |
| Playful & Silly | Under the Sea, Ice Kingdom, Circus Town | Cherry Twinkle |

---

## How It Works

All stories and audio are pre-generated and served as static files — no backend, no API keys in the browser, no internet required after the first load.

```
storytime-app/
├── index.html          # The entire app
├── stories.json        # 256 AI-generated stories
├── audio/              # 256 MP3s + 256 timestamp JSON files
│   ├── leo_beach.mp3
│   ├── leo_beach.json
│   └── ...
└── sounds/             # Sound effect clips
```

---

## Regenerating Content

If you want to generate your own stories and narration, you'll need API keys for [Anthropic](https://console.anthropic.com) and [ElevenLabs](https://elevenlabs.io).

**1. Generate stories**
```bash
# Mac/Linux
ANTHROPIC_API_KEY=sk_xxx python3 generate_stories.py

# Windows
set ANTHROPIC_API_KEY=sk_xxx
python generate_stories.py
```
Produces `stories.json` with all 256 stories. Resume-safe — re-run if interrupted.

**2. Generate narration**
```bash
# Mac/Linux
ELEVENLABS_API_KEY=sk_xxx python3 generate_narration.py

# Windows
set ELEVENLABS_API_KEY=sk_xxx
python generate_narration.py
```
Produces an `audio/` folder with one `.mp3` and one `.json` per story. Resume-safe.

**3. Test voices (optional)**
```bash
python test_voices.py
```
Generates 4 sample MP3s — one per narrator — before committing to the full run.

---

## Install on iPad

1. Open the live link in **Safari**
2. Tap the **Share** button
3. Tap **Add to Home Screen**
4. Tap **Add**

The app opens fullscreen with no browser bar, just like a native app.

---

## Built With

- [Anthropic Claude](https://anthropic.com) — story generation
- [ElevenLabs](https://elevenlabs.io) — text-to-speech narration and word timestamps
- [freesound.org](https://freesound.org) — sound effects
- Vanilla HTML, CSS, JavaScript — no frameworks
- GitHub Pages — hosting

---

## License

MIT — free to use, modify, and share.
