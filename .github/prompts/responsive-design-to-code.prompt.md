---
agent: design-to-code
---
Get the selected frame in Sketch and generate the HTML and CSS using only values extracted from Sketch. 

If the selected frame is nested inside a parent frame, also extract the parent frame to get context like background colors and overall page styling.

For the icons use phosphor icons the CDN is `https://unpkg.com/@phosphor-icons/web`

After generating the first pass, immediately refactor the output to be responsive, while keeping the same visual style and structure:

- spacing stays comfortable on small screens
- elements wrap or stack instead of being squeezed
- text remains readable
- the component still looks balanced and intentional

Responsive rules:
- Avoid fixed widths/heights on outer containers and layout wrappers (e.g. card shells, page wrappers). Prefer:
  - `max-width`, `width: 100%`, `min-width`, `min-height`
  - flexbox/grid with `gap`
  - `flex-wrap: wrap` where appropriate
  - sensible `flex` values (e.g. `flex: 1`, `flex: 0 0 auto`)
- Keep fixed dimensions only when they are semantically required (e.g. icons, avatars, deliberate aspect ratios, small controls).
- Where a fixed Sketch width exists, convert it into a responsive constraint:
  - `max-width: <sketch width>px; width: 100%;`
- Ensure text doesn’t overflow:
  - use `max-width`, `min-width: 0` on flex children when needed
  - allow wrapping (avoid forcing `white-space: nowrap` unless essential)
- Add only the minimum media queries needed (aim for 1–2 breakpoints, start around 700px).
- Only change what is necessary to fix responsiveness. Do not redesign.

Output:
- Provide final HTML and CSS.
- If you changed any width/height rules, briefly list what you changed and why (1–6 bullets).