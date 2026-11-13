# NEON SIEGE 3D

A wave-survival arena shooter that runs in the browser — built with Three.js (WebGL), no build step, no backend.

**Play:** open the GitHub Pages URL, or open `index.html` directly.

## Controls

| Action | Desktop | Touch |
| --- | --- | --- |
| Move | `W A S D` / arrow keys | left stick |
| Aim | mouse | right stick |
| Fire | hold left mouse (or `J`) | right stick (auto-fire) |
| Dash | `Space` / `Shift` | — |
| Pause | `Esc` / `P` | — |
| Mute | `M` / AUDIO button | AUDIO button |

## What's in it

- **Five enemy types** — grunts, fast swarms, ranged spitters, armoured tanks, and a boss every 5th wave that fires radial bursts and summons adds.
- **Wave scaling** — enemy HP, speed and spawn density climb with each wave.
- **Upgrade bay** — credits from kills buy eight stacking upgrades (damage, fire rate, split barrel, piercing rounds, thrusters, hull plating, phase drive, nano repair).
- **Swept collision** — bullets are tested as line segments, so shots never tunnel through enemies on low-framerate machines.
- **Procedural audio** — every sound is synthesised with the Web Audio API; there are no audio files to load.
- **Installable PWA** — `manifest.webmanifest` + `sw.js` make it installable and playable offline after the first visit.
- **Local best score** saved in `localStorage`.

## Files

```
index.html              the entire game (HTML + CSS + ES module)
manifest.webmanifest    PWA manifest (name, icons, fullscreen)
sw.js                   service worker: caches the shell for offline play
icon-192.png            app icon
icon-512.png            app icon (also used as maskable)
```

## Notes

- Three.js is loaded from a CDN via an import map, so the **first** load needs a connection. After that the service worker serves it from cache.
- Shipping an update: bump `CACHE` in `sw.js` (e.g. `neon-siege-v2`) so returning players get the new build.
- `window.__S` exposes live game state in the console if you want to poke at it while tuning.
