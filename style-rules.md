# VectorCraft toolbar style rules

## Grid and optical bounds

Use a `0 0 24 24` viewBox and a 24-unit master. Keep visible ink inside the 2-unit optical inset, including the 0.8-unit half-stroke. Place ordinary stroke centerlines at least 2.8 units from the edge. Center simple shapes by their visual mass. Allow asymmetric tool silhouettes to lean toward their action direction without filling the viewBox.

Use decimals to adjust spacing. Avoid snapping a diagonal tool to integer coordinates at the expense of a clear counter. Do not add an enclosing tile to the glyph itself; the interface owns the hit target and state background.

## Stroke, caps and corners

Use a 1.6-unit stroke with round joins. Use round caps on open paths and restrained short endpoints; do not simulate bristles or rays with clusters of tiny strokes. Keep geometric rectangle corners square unless rounding describes the tool, as with rounded rectangles, controls or a physical handle. Rounded control containers use 0.4–1.0-unit corner radii; the rounded-rectangle tool uses a larger radius.

Keep a continuous path where the function describes continuity: spline, arc, spiral and path baselines. Use endpoint handles only if they carry meaning. A construction node may be a solid dot; a selectable anchor may be an open square.

## Fill and counters

Default SVG ink is `#e3e7ed`; transparent regions remain unpainted. Use one ink per glyph. Selection uses solid mass; direct selection uses a hollow version of the same custom pointer. Keep the fill helper stroke-free. A pointer or nib remains generic interaction vocabulary; new coordinates alone do not establish a distinct visual identity.

Use fill where it names behavior: blob paint, liquid drops, a filled region, an area series or changed symbol appearance. Keep holes open rather than painting them with a background color. Do not use gradients, shadows, glows, font text, embedded images or external resources. A functional flare can use lens rings and short rays; do not add decorative sparkle.

## Small sizes

Scale the master to 20 and 16 px. That yields a 1.333 px and 1.067 px stroke. Do not use `vector-effect="non-scaling-stroke"`, which would make the small glyphs heavier than the master.

Aim for a 2-unit clear gap between independent details and broad counters in the primary silhouette. Check open anchors, nib breathers, symbol diamonds and graph interiors in actual 16/20/24 px renders. Merge or remove subordinate detail during an optical revision if those counters close; retain the operation-defining mark. These assets have one master each, not separate pixel-hinted size variants. Raster proof and acceptance belong to the review; the construction review does not claim small-size validation.

Keep the following distinctions visible: solid/hollow pointer; pen plus/minus; area/path/vertical text; brush tuft/blob puddle; open drawing spiral/directional twirl; round scallop/angular crystallize/irregular wrinkle; ruler/linked dimension; symbol shift/scrunch/size/spin/stain/screen/style. Do not replace an unfamiliar tool with a generic box or sparkle.

## Light and dark themes

Recolor all non-transparent ink together. Parent proof palette:

| Role | Medium-dark | Light |
| --- | --- | --- |
| Panel | `#272c36` | `#f3f5f8` |
| Icon | `#ccd3de` | `#2a303b` |
| Text | `#e4e9f1` | Use the interface text token |
| Hover surface | `#353c49` | Use the interface hover token |
| Active surface | `#3d4553` | Use the interface active token |
| Accent | `#f06a52` | Use the interface accent token |

Do not bake these surfaces into the glyphs. The SVG default ink supports a neutral dark proof; it is not a fixed production color requirement. Review hollow counters against each panel background. Existing runtime selection underpainting uses a black/white helper, so the reviewer must decide how that behavior fits the new solid/hollow treatment before any integration.

## Hover, active and disabled

Keep geometry and stroke width unchanged across states. Hover uses the surface token. Active uses the active surface plus an interface-owned accent marker or focus treatment; do not recolor one part of an icon or fill an otherwise hollow glyph to indicate selection. Keep tool semantics separate from button state.

Disabled uses the same geometry with the interface disabled foreground token or whole-glyph opacity. Reduce the complete glyph, including fills and strokes, by the same amount. Keep the label and disabled reason available; opacity alone does not explain unavailable behavior. Keyboard focus uses an external focus ring without altering the glyph.

## Ownership and proposals

`toolbar-manifest.json` records absolute SVG paths, generic functions, construction rationale and uncertainties. The inherited ids remain stable for current aliases. The `proposal-` ids provide distinct artwork for roles whose current mapping shares an icon or falls back to a generic missing-icon image. They require future mapping decisions; this design task changes no application code. Keep these proposals distinct from production-ready mapping claims.
