# Heaven.

A cinematic, fully procedural vision of heaven at golden hour — floating meadow
islands pouring waterfalls of liquid gold light into an endless mist, luminous
birds wheeling between them, and a colossal crystal gate burning far across the
haze. The air itself knows where the sun is: haze turns gold looking sunward
and dusty rose away, clouds ignite along their backlit fringes, and crepuscular
rays stream past the islands when you gaze into the light.

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

| Input | Action |
| --- | --- |
| *(none)* | Cinematic auto-tour: orbits, a dive down a fall of light, a pass beneath the islands, and the long drift toward the gate |
| Click an island | Behold it — glide into a slow orbit; click it again (or open sky) to drift on |
| Click the gate / `E` | Enter the Source — a cinematic approach and pass-through |
| `C` | Toggle free-fly |
| Click | Capture the mouse (free-fly) — if the browser refuses (just pressed Esc / window unfocused), **hold and drag** to look instead |
| `W A S D` | Move |
| `Space` / `Q` | Rise / sink |
| `Shift` | Fly fast |
| `H` | Re-show the help hint |
| `Esc` | Release the mouse / abort the gate sequence |

### PS5 / gamepad (standard mapping)

| Input | Action |
| --- | --- |
| Left stick | Fly (moving a stick during the tour enters free-fly) |
| Right stick | Look |
| `R2` / `L2` | Rise / sink |
| `R1` | Fly fast |
| ✕ | Behold the island you face / enter the gate |
| ◯ | Return to the tour |
| Options | Toggle free-fly |

## Notes

- **Adaptive quality, both ways**: a five-rung ladder (0.8×–2.0× render scale,
  MSAA 0–4×) steps down when frames sag past your display's own refresh
  interval and back up after sustained headroom — strong GPUs get
  supersampling, weak ones survive. Honors `prefers-reduced-motion`.
- Post-processing: HDR bloom, screen-space crepuscular rays (high tiers),
  filmic split-tone grade with highlight-to-white rolloff, aspect-true
  vignette, always-on dither, auto-iris exposure, and a screen-space lens
  flare with an anamorphic streak.
- Targets 60 fps on a mid-range laptop: instanced grass/crystals/birds, merged
  geometries, instance-aware frustum culling, no shadow maps, fog-limited draw
  distance.
