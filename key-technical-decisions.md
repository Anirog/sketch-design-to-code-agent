## 🔑 Key Technical Decisions

**Stack Layout → CSS Flexbox**

Sketch's **Stack Layout** system is essentially a visual flexbox builder. Our agent maps these properties:

```
// From Sketch Stack Layout
{
  direction: 1,           // Row (column = 0)
  justifyContent: 1,      // Center
  alignItems: 1,          // Center
  gap: 0,
  padding: { horizontal: 40, vertical: 8 }
}

// To CSS Flexbox
{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 0px;
  padding: 8px 40px;
}
```

---

## 🐞 The Philosophy: Null Values Are Features, Not Bugs

The most important discipline we enforced is respecting `null` values:

```
// ❌ BAD - Guessing defaults
cornerRadius: cornerRadius ?? 8, // Assumes 8px if missing

// ✅ GOOD - Respecting missing data
cornerRadius: cornerRadius ?? null, // Null means "not set in Sketch"
```

### Why this matters:

- **Design Intent**: If a property is `null`, it means the designer didn't set it. Guessing contradicts that intent.
- **Debugging**: A `null` value is a clear signal to ask "what should this be?" rather than silently applying a default
- **Precision**: Every CSS value comes from Sketch, making the generated code production-ready
- **Discoverability**: Missing `null` values in the extraction JSON tell you exactly what properties need to be added to your Sketch design

This discipline prevents the most common design-to-code problem: **invented values that never existed in the design system**.

## API Integration Points
The agent uses these Sketch API methods extensively:

```
const document = sketch.getSelectedDocument();
const selection = document.selectedLayers.layers;

// Each layer provides:
layer.frame              // Geometry (x, y, width, height)
layer.style.fills        // Colors with blend modes
layer.style.borders      // Strokes
layer.style.shadows      // Shadow effects
layer.style.blurs        // Blur effects
layer.stackLayout        // Flexbox-like layout
layer.blendMode          // Layer blend mode
layer.cornerRadius       // Border radius
```
