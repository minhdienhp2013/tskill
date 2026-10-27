# Print production and quality checks

Use this reference when the user intends to print the result or asks for high-resolution output.

## Confirm the physical format

- Record finished width and height, orientation, number of sides/pages, and intended output format.
- Preserve a usable source document's page size unless the user asks for a change.
- Follow the print shop's supplied bleed, safe-area, color, and PDF requirements. Do not assume that every shop accepts the same values.
- If production specs are unavailable, label the result as a print-oriented proof and state which specs remain unconfirmed.

## Keep vector content vector

- Keep titles, body text, prices, diagram nodes, connectors, borders, and simple decorative geometry as vector text/shapes.
- Use fonts with Vietnamese glyph coverage. Embed fonts in PDF when the export path supports it; verify diacritics in the rendered output.
- Use raster images only where continuous-tone artwork, photography, or generated texture is appropriate. Check resolution at its placed size.
- Do not rasterize the entire page merely to claim 4K. If the user also needs a PNG, export a separate raster preview at a stated pixel size.

## Raster resolution

Calculate effective resolution from the placed dimensions: pixel width or height divided by the corresponding print dimension in inches. Prefer the printer's requested PPI. If none is given, explain the chosen value and note that fine detail, viewing distance, paper, and print process affect what is suitable. Do not treat PPI metadata alone as added detail.

## PDF review

Render every page and inspect the actual page images. Check:

- page dimensions, orientation, and front/back order;
- clipped text, missing glyphs, overlaps, cramped spacing, and small type;
- exact spelling and punctuation against the locked source text;
- diagram parent-child links, arrow direction, and reading order;
- margins, trim and bleed areas when specified;
- image sharpness, contrast, transparency, and color consistency.

Extract PDF text where possible and compare it with the locked content inventory. Text extraction cannot confirm visual layout, so always pair it with rendered-page inspection.

## Color and handoff

- Do not claim CMYK or a specific color profile unless the file was exported and checked with the required profile.
- Do not claim PDF/X compliance without a suitable preflight check.
- Hand off the vector PDF, an editable SVG when appropriate, and a PNG preview if useful. State any raster artwork embedded in the vector-first file and any unconfirmed print-shop requirements.
