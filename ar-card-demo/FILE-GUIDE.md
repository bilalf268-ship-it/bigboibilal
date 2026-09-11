# AR Property Card — File Guide

You now have **two versions** in separate folders. Use whichever matches your
situation — you don't need both.

---

## Version 1: `ar-card-demo/` — single project, straight to AR
Use this if a card only ever needs to show ONE project.

| File | What it's for |
|---|---|
| `index.html` | The whole app. NFC tag / QR code should point straight to wherever you host this. |
| `hiro.png` | Placeholder FRONT-of-card image (shows the building). |
| `unit-marker-source.png` | Placeholder BACK-of-card image (shows the unit). |
| `unit-marker.patt` | Tracking data for the back image. `ar.html`/`index.html` loads this automatically — you never open it directly. |
| `printable-sample-card-sheet.png` | Print this to test both sides on paper right now. |

**Flow:** NFC tap → `index.html` loads → camera opens → point at front square → building
appears → flip to back square → unit appears.

---

## Version 2: `ar-card-demo-multi-project/` — one card, multiple projects
Use this for a builder with several active projects. This is the one we just
built together.

| File | What it's for |
|---|---|
| `landing.html` | **This is what the NFC tag should point to.** Shows the builder's logo + a tappable list of projects. |
| `ar.html` | The AR viewer. Opens automatically when a project is tapped on `landing.html` (it reads which project was picked from the link, e.g. `ar.html?project=harbor`). You never link to this directly. |
| `hiro.png` | Placeholder FRONT-of-card image, shared across all projects for now. |
| `unit-marker-source.png` | Placeholder BACK-of-card image, shared across all projects for now. |
| `unit-marker.patt` | Tracking data for the back image, used automatically by `ar.html`. |
| `printable-sample-card-sheet.png` | Print this to test — same physical card works for all 3 sample projects, since the content is chosen on the landing screen, not the card. |

**Flow:** NFC tap → `landing.html` loads → tap "Harbor Point" → `ar.html?project=harbor`
loads → camera opens → point at front/back of the SAME printed card → Harbor
Point's building/unit appear (color-coded placeholders for now).

**Bug I caught and fixed:** the version of `landing.html` I described earlier
was never actually saved for you, and it linked to a page (`ar.html`) that
didn't exist yet. Both are now built and included here — tested end to end.

---

## Hosting (needed either way)
Phone cameras require HTTPS — pick ONE:
- **GitHub Pages** (free): new repo → enable Pages in Settings → upload the
  files from whichever version folder you're using, keeping filenames as-is.
- **Netlify Drop** (free, no account needed): netlify.com/drop → drag the
  folder in → get an instant HTTPS link.

Whichever URL you get, that's the one you write to the NFC tag — `landing.html`'s
URL for the multi-project version, `index.html`'s URL for the single-project one.

## Next steps (same as before)
- Send real card artwork → I regenerate the tracking patterns from it.
- Send real `.glb` 3D models per project → I swap them in for the placeholder shapes.
- For the multi-project version, send the actual project names/photos for the
  picker list and I'll replace the 3 sample entries.
