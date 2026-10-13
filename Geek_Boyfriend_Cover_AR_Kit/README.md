# Geek Boyfriend — Page-Tracked Cover AR (starter)

This starter uses **MindAR 1.2.5** + **A-Frame 1.6.0** (no mobile app installation). It attaches simple butterflies, twinkling stars, and a small 3D satellite to a real printed book cover. It is a working *template*, **not yet tested on a physical phone**; you must first compile your chosen final cover into `targets.mind` using the compiler.

## Choose the cover

The folder `cover_choices/` contains three previously generated sample cover illustrations:

1. `option_1_umbrella.png` — rainy city, umbrella
2. `option_2_cafe.png` — two characters at a cafe table
3. `option_3_bookshop.png` — bookshop, pink shirt, laptop

**Choose exactly ONE.** The tracking works best when the physical cover is visually identical to the uploaded target image, including title placement and decorative elements. If you later edit or crop the final cover, recompile it.

## Step 1 — Compile the target

1. Open <https://hiukim.github.io/mind-ar-js-doc/tools/compile/> on a desktop browser.
2. Upload the chosen book cover PNG.
3. Click **Start** and wait for the target-feature preview.
4. Click **Download**, and rename the downloaded file **`targets.mind`** if necessary.
5. Put it inside the `cover-ar/` folder next to `index.html`.

## Step 2 — Upload to your existing GitHub Pages repository

Your existing repo: <https://github.com/gima2003/geek-boyfriend-ar>

- Open the repository -> **Add file -> Upload files**.
- Upload the entire contents of the `cover-ar/` folder, preserving these relative paths:

```
geek-boyfriend-ar/
  index.html                    <-- your existing Episode 18 site: do not change
  targets.mind                  <-- existing Episode 18 target: do not change
  cover-ar/
    index.html
    targets.mind                <-- NEW: compiled from the actual book cover
    assets/
      butterfly_coral.png
      butterfly_lavender.png
      sparkle.png
```

On GitHub's browser uploader, dragging the `cover-ar` folder into the upload area should preserve subdirectories. Verify the resulting folder tree before committing.

- Click **Commit changes**.
- Your new AR page should be:

  <https://gima2003.github.io/geek-boyfriend-ar/cover-ar/>

**Important:** The `/cover-ar/` subfolder is a DIFFERENT AR experience from your previously deployed Episode 18 prototype. Do not upload the new compiled `targets.mind` to the repository root or you'll break Episode 18.

## Step 3 — Test

1. Print your chosen cover or show its original PNG (full image) on a laptop screen.
2. Open the `cover-ar` URL on an Android Chrome browser or iPhone Safari browser.
3. Allow camera permission.
4. Aim the phone at the FULL cover; do not aim the camera at the QR code.
5. You should see butterflies, stars and a satellite anchored to the cover. Slowly tilt your phone or the book.
6. If the animation is not visible, move the camera back a little so the whole cover fits, remove glare, and ensure the target `.mind` matches the artwork.

### Troubleshooting

- Website 404 -> GitHub Pages not deployed yet or wrong path.
- Infinite loading -> missing/corrupted `targets.mind` or camera/browser init failure; inspect browser console.
- Camera permission denied -> enable site camera permissions; browser needs HTTPS.
- Camera open but no animation -> image recognition issue: exact target, no glossy reflection, good lighting, full page visible, target compiled using proper image.
- Animations visible but float/jitter -> slow the camera and use a rigid, flat cover; refine tracking filter settings later.

## Next improvements

The first version adds independent *overlay assets*, not genuinely animated people extracted from the original illustration. To achieve the example you showed (flowers emerging from cover, characters at layered depths), the next step is to make transparent image layers (cutouts) for characters and plants, then add them as textured A-Frame planes positioned at different Z depths. For true 3D characters, import licensed or original GLB models and animate with skeletal animation in Blender. Add music only after user interaction due to mobile browser audio policies.

Before printing copies: decide final physical trim size, prepare proper print-resolution artwork with bleed, test glossy vs matte stock, and ensure the QR/link remains maintainable long term. These sample images are prototypes rather than verified press-ready covers.

Software reference: <https://hiukim.github.io/mind-ar-js-doc/quick-start/overview/>.
