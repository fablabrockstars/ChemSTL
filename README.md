# BS to STL

Browser tool: load an XBS `.bs` ball-and-stick file, preview it in 3D, export a scaled binary STL.
Everything runs client-side; files never leave the browser.

## Host on GitHub Pages
1. Create a repo and add `index.html`, `example.bs`, `.gitattributes` (this README is optional).
2. Settings > Pages > Build and deployment > Deploy from a branch > `main` / `/ (root)`.
3. Open `https://<user>.github.io/<repo>/`.

Local test: `python3 -m http.server` in this folder, then open http://localhost:8000
(three.js loads from jsDelivr, so you need an internet connection).

## Sizing rule
- The carbon `spec` radius in the `.bs` file becomes the **Carbon radius** you enter (default 22 mm).
  That sets one uniform scale for the whole file, so atom spacing and the other elements keep the
  file's own proportions.
- Bond thickness is set directly in mm (default 6 mm, as diameter; switch to radius if you meant that).

## Notes
- Balls and sticks are separate closed shells that overlap; slicers union them when slicing.
- `.gitattributes` marks `*.stl` as binary so git never rewrites line endings inside STL files.
