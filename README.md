# Heaven.

A cinematic, fully procedural vision of heaven at golden hour — floating meadow
islands pouring waterfalls of liquid gold light into an endless mist, luminous
birds wheeling between them, and a colossal crystal gate burning far across the
haze.

Everything lives in a single file: **`index.html`**. No build step, no assets —
geometry, textures, clouds, and light are all generated in code. Three.js is
pulled from the jsDelivr CDN.

## Run it

Open `index.html` in any modern browser (double-clicking the file works), or
serve it locally:

```
python3 -m http.server
# → http://localhost:8000/index.html
```

## Controls

| Key | Action |
| --- | --- |
| *(none)* | Cinematic auto-tour: orbits, a dive down a fall of light, a pass beneath the islands, and the long drift toward the gate |
| `C` | Toggle free-fly |
| Click | Capture the mouse (free-fly) |
| `W A S D` | Move |
| `Space` / `Q` | Rise / sink |
| `Shift` | Fly fast |
| `Esc` | Release the mouse |

## Notes

- Targets 60 fps on a mid-range laptop: instanced grass/crystals/birds, merged
  geometries, no shadow maps, fog-limited draw distance, and an adaptive
  pixel-ratio step-down if the frame rate sags.
- Post-processing: HDR bloom, golden-white grade, soft vignette, and a
  screen-space lens flare on the sun.
