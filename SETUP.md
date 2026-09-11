# AR Property Card — Working Demo

## What's in this folder
- `index.html` — the AR web page (front → building, back → unit)
- `unit-marker.patt` — tracking data for the "back of card" pattern (generated for you)
- `unit-marker-source.png` — the back-of-card marker image
- `printable-sample-card-sheet.png` — print this to test both sides right now
- `hiro.png` — the front-of-card marker (standard AR.js test pattern)

## 1. Test on your phone (5 minutes)
Phone cameras require the page to be served over **HTTPS** — it won't work opened
straight from a file. Easiest free option:

1. Create a free GitHub account (if you don't have one) → new repository → enable
   **GitHub Pages** in Settings.
2. Upload all files in this folder to that repository, keeping the same file names.
3. GitHub gives you a URL like `https://yourname.github.io/repo-name/`
4. Open that URL on your phone, allow camera access.
5. Print (or just display on a second screen) `printable-sample-card-sheet.png`,
   point your phone at the FRONT square → placeholder building appears.
   Flip to the BACK square → placeholder unit appears.

(Netlify Drop — netlify.com/drop — is another free, drag-and-drop option if you'd
rather skip GitHub.)

## 2. Once you send real card artwork
Send me the final front and back images (high-contrast, detail-rich renders work
best for tracking). I'll regenerate `unit-marker.patt` (and a matching one for the
front, replacing the Hiro placeholder) from your actual artwork, so the card itself
becomes the marker instead of the placeholder patterns.

## 3. Once you have real 3D models
Send `.glb` files (from Blender, SketchUp, Revit export, or your 3D artist) and I'll
swap them in for the placeholder box-shapes, keeping the same flip-to-switch behavior.

## 4. NFC card
Once the page is live at a permanent URL, write that URL to an NTAG213/215 NFC
inlay using the free "NFC Tools" app (iOS/Android), then set the tag to read-only.
Sandwich the inlay between your two printed card layers as planned.
