---
name: alansari-motion-library
description: Applies named motion graphics presets (M-001 to M-1000) and fonts (FA-xx Arabic, FE-xx English) from the Alansari.Tech Motion Library when editing Reels, TikTok or Shorts videos. Use whenever the user names a motion by ID or name (for example M-016, Circle Reveal, Fade Up), says مكتبة الموشن or طبّق حركة, asks for a font by ID (FA-02, FE-10) or name, or gives a line and says which motion to apply on it.
---

# Alansari.Tech Motion Library

The user edits vertical videos (1080x1920, 30fps) and names motions and fonts by ID.
Apply exactly what the library specifies. The library files are the source of truth.

## Step 1: find the entry
The full library ships with this plugin (it updates whenever the plugin syncs):
- `references/alansari-motion-library-ar.md` (Arabic descriptions, read this first)
- `references/alansari-motion-library.md` (English descriptions)
- `references/alansari-motion-library.json` (machine-readable, includes the Fonts list with file URLs)

Search for the ID or name the user gave (for example grep for `M-016` or `FA-02`) and read only that entry. Do not load the whole file.

Optionally, if web access is available, the newest published copy is at
https://alansariteach.github.io/motion-library/alansari-motion-library-ar.md
Use it only if it differs from the bundled entry.

## Step 2: apply it
- Follow the entry's Spec, Duration and Easing exactly.
- Read "Content the user must provide". If the user did not give that content (text, image, logo, handle, screen recording), ask for it before rendering. Never invent logos, screenshots or numbers.
- Variants (Fast, Slow, Gold, Boxed) need the same content as their base motion.
- Start the motion on the exact frame of the word or action the user names (use word-level timestamps).
- Keep text inside the Reels safe zone: y 300 to 1550, x 60 to 1020.
- Motions can be chained: "M-016 then M-038".
- Fonts: use the Fonts table entry (ID, name, Google Fonts link, file URL). Use an Arabic font (FA-xx) for Arabic text. Download and register the font before rendering.

## Step 3: check
Export stills of each motion moment and check timing, overlaps and the safe zone before the final render.

## Notes
- Motion names are English and fixed. Use them as written.
- Reply in the language the user writes in (usually Gulf Arabic).
- Visual examples: https://alansariteach.github.io/motion-library/ (button: معاينة المثال).
