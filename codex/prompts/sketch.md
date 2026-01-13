---
description: Design to Code prompt for generating responsive HTML/CSS from Sketch designs.
---
Get the selected frame in Sketch and generate HTML and CSS using only values extracted from Sketch.
For icons, use Phosphor Icons via the CDN: `https://unpkg.com/@phosphor-icons/web`.

Write the results to files in the current working directory.

Derive the base filename from the selected Sketch layer name (kebab-case):
- <name>.html
- <name>.css

After generating the first pass, immediately refactor the output to be responsive, while keeping the same visual style and structure:
- spacing stays comfortable on small screens
- elements wrap or stack instead of being squeezed
- text remains readable
- the component still looks balanced and intentional

Responsive rules:
- Avoid fixed widths/heights on outer containers and layout wrappers. Prefer `max-width`, `width: 100%`, flex/grid with `gap`, and `flex-wrap`.
- Keep fixed dimensions only when semantically required (icons, avatars, small controls, deliberate aspect ratios).
- Where a fixed Sketch width exists, convert it into: `max-width: <sketch width>px; width: 100%;`
- Prevent overflow: use `min-width: 0` on flex children when needed and allow wrapping.
- Use only 1–2 media queries (start around 700px).
- Only change what is necessary to fix responsiveness. Do not redesign.

Output:
- Save the final HTML and CSS to the files above.
- Briefly list any width/height changes (1–6 bullets).