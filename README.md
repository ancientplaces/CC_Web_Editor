# Chroma Console — Web MIDI Editor

A browser-based editor for the [Hologram Chroma Console](https://www.hologramelectronics.com/chroma-console). Control and tweak every parameter from your browser over USB MIDI — no app to install, no drivers needed.

> ⚠️ **Early testing release.** This is a work in progress and likely has bugs I'm not yet aware of. If something behaves unexpectedly, please let me know.

---

## Browser Compatibility

| Browser | Works? |
|---|---|
| **Chrome** ✅ | Full support |
| **Edge** ✅ | Full support |
| Firefox ❌ | Web MIDI API not supported |
| Safari ❌ | Web MIDI API not supported |

**You must open the editor over `http://` or `https://`** — not from a local `file://` path. If you've been sent a hosted link (e.g. Netlify or GitHub Pages), just open it in Chrome or Edge and you're good to go.

---

## Connecting Your Chroma Console

1. **Connect via USB-C** — plug a USB-C cable from your Chroma Console to your computer. The pedal is class-compliant, so no drivers are required. Your OS will detect it automatically.

2. **Open the editor** in Chrome or Edge.

3. **Grant MIDI access** — your browser will ask for permission to use MIDI devices. Click **Allow**.

4. **Select your device** — use the **Out** and **In** dropdowns in the status bar at the top of the page:
   - **Out** → select *Chroma Console* (sends your edits to the pedal)
   - **In** → select *Chroma Console* (receives changes from the pedal's own knobs)

5. **Select your MIDI channel** — use the channel selector on the right panel. This should match the MIDI channel configured in the pedal's Global Settings (default is Ch 1).

Once connected, the status dot in the top-left will turn green.

---

## What the Controls Do

| Control | Description |
|---|---|
| **Knobs** (arc dials) | Drag up/down, or scroll with the mouse wheel. Double-click to reset to default. |
| **Module selectors** | Choose the effect algorithm for each section (Character, Movement, Diffusion, Texture). |
| **Filter Mode** | LPF / Tilt / HPF — switches the pedal's filter character. |
| **Capture Transport** | Stop, Play, Record, All Off — controls the pedal's looper/capture engine. |
| **Pedal Bypass** | Toggles the pedal in/out of bypass. |
| **Min / Mid / Max** | Snaps all knobs to 0, 64, or 127 at once. |
| **Random** | Randomises all knob values — good for happy accidents. |

---

## Known Limitations & Caveats

- **Bidirectional sync on connect** — the editor does not yet request the pedal's current state on connection. The display will sync as soon as you move a knob on the pedal, but initial values may not reflect what's loaded on the hardware.
- **No preset save/load** — preset management is not yet implemented.
- **USB MIDI only** — this editor communicates over USB. The pedal's 5-pin DIN MIDI port operates independently and is not used here.
- **Chrome/Edge only** — Firefox and Safari do not support the Web MIDI API and cannot use this tool.

---

## Hosting This Yourself

The editor is a single self-contained `index.html` file — all fonts are embedded, there are no external dependencies. To share it:

- **Netlify Drop**: Go to [app.netlify.com/drop](https://app.netlify.com/drop) and drag the file onto the page. You'll get a shareable `https://` URL in seconds.
- **GitHub Pages**: Push `index.html` to a repository and enable Pages under *Settings → Pages*.

---

## Credits & Licensing

**Fonts** embedded under the [SIL Open Font License 1.1](https://scripts.sil.org/OFL):
- [Inter](https://rsms.me/inter/) by Rasmus Andersson
- [JetBrains Mono](https://www.jetbrains.com/lp/mono/) by JetBrains

This tool is an unofficial, community-built utility and is not affiliated with or endorsed by Hologram Electronics.
