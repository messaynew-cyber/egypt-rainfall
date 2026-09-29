# Egypt — Rainfall Reality

An interactive **Three.js** visualization of Egypt's annual precipitation.

> Egypt gets an average of **~20 mm of rain per year**. Cairo — 22 million people —
> gets 25 mm. Aswan gets **zero**. The entire country runs on a river that
> flows in from somewhere else.

**Live:** https://messaynew-cyber.github.io/egypt-rainfall/

---

## The data drives the geometry

Three independent encodings, all from Egyptian Meteorological Authority /
WMO climate normals. Nothing here is decorative.

| Encoding | Meaning |
|---|---|
| **Pillar height** | Annual precipitation in mm/yr |
| **Particle count** | Number of rain *events* per year |
| **Particle style** | Drizzle (Mediterranean) vs. flash flood (Upper Egypt) |

### Climate normals used

| City | Lat | mm/yr | Events/yr | Character |
|---|---|---|---|---|
| Alexandria | 31.20 | **180** | 22 | Winter frontal drizzle |
| Port Said | 31.26 | **90** | 12 | Coastal winter rain |
| Cairo | 30.04 | **25** | 4 | The "wet" part of Egypt |
| Fayoum | 29.31 | **12** | 2 | Marginal |
| Asyut | 27.18 | **2** | 1 | Effectively nothing |
| Luxor | 25.69 | **1** | 1 | Torrential, ~once a decade |
| Aswan | 24.09 | **0** | 0 | Literally never |

### Why Aswan has no particle system

It isn't an oversight. Aswan averages **0 mm/yr** and has recorded
decade-long stretches with no measurable precipitation. The absence of
particles *is* the data.

### Why Luxor has one event but 260 particles

Upper Egypt doesn't get drizzle — it gets nothing for years, then a
convective burst that flash-floods a wadi and drowns a village. One
event per year, maximum violence. The visualization renders it brighter,
larger, and falling from higher, because that's what it does.

---

## Features

- **Real lon/lat projection** — the Nile is drawn along actual coordinates
- **Cycle Year** — simulates a full year at 42 days/sec, announcing each rain event
- **Rain / Nile toggles** — turn the Nile off and watch the country become uninhabitable
- **Touch orbit** — drag to rotate, pinch to zoom (OrbitControls with damping)
- **Auto-orbit** on load so it reads well on a phone screen
- **Zero build step** — single HTML file, Three.js from CDN via importmap

## Run it locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Needs network access for the Three.js CDN (jsdelivr).

## The point

Two things this makes obvious that a rainfall table doesn't:

1. **The gradient is brutal and it's geographic.** Rainfall in Egypt is a
   Mediterranean phenomenon that dies within 300 km of the coast. The
   country's population, however, is strung along a river running through
   the part with no rain.
2. **Aswan's zero isn't "low rainfall."** It's a different category of
   reality. Some years the sky over Aswan does nothing at all.

Turn off the Nile layer. That's Egypt without one river.

## License

MIT — the climate data is public domain, the visualization is yours.
