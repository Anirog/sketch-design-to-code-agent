---
description: Design to Code prompt for generating HTML/CSS for a single component from Sketch.
---
Get the selected frame in Sketch and generate HTML and CSS using only values extracted from Sketch.

Assume the selection represents a single, self-contained component (for example: button, pill, badge, icon wrapper).

For icons, use Phosphor Icons via the CDN: `https://unpkg.com/@phosphor-icons/web`.

Do not refactor or reinterpret for responsiveness unless strictly required by the extracted Sketch constraints.

Write the output to files in the current working directory.

Derive the base filename from the selected Sketch layer name (kebab-case):
- <name>.html
- <name>.css