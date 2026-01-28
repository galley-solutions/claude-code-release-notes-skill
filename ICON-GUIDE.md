# Galley Icon & Illustration Visual Guide

This guide documents the icon and illustration style for Galley release notes and marketing materials.

## Figma Source File

**Primary Reference:**
[Galley Visual Identity System (VIS)](https://www.figma.com/design/jBKuWmEGuoa68OKfOcS2PD/Galley_Irene-s-Work?node-id=5613-8569)

### Relevant Pages in Figma

| Section | Pages | Description |
|---------|-------|-------------|
| **Iconography** | pg 13-21, Extra 1-2 | Main icon library |
| **Galley Assist Icons** | GA 6-15 | AI/Assistant-specific icons |
| **Illustrations** | pg 11-12 | Full illustrations |
| **Galley Assist Illustrations** | GA 4-5 | AI-themed illustrations |
| **Imagery** | pg 7-10 | Photography and imagery guidelines |

---

## Icon Style Guidelines

### Visual Characteristics

| Property | Specification |
|----------|---------------|
| **Style** | Hand-drawn, organic, sketch-like |
| **Stroke Weight** | Consistent, medium weight |
| **Stroke Color** | Icon Stroke `#1A1A18` (dark, almost black) |
| **Fill Colors** | Galley Green `#2F4F4F`, Sprout `#d4dfc8`, or color accents |
| **Corners** | Rounded, soft edges |
| **Mood** | Warm, approachable, culinary-focused |

### Color Usage in Icons

| Color | Hex | Usage |
|-------|-----|-------|
| **Icon Stroke** | `#1A1A18` | All outlines and line work |
| **Galley Green** | `#2F4F4F` | Primary fill color |
| **Sprout** | `#d4dfc8` | Secondary/background fill |
| **Dark Sprout** | `#9AB47E` | Accent fill |
| **Pumpkin** | (orange accent) | Highlight accents |
| **Nutmeg** | (brown accent) | Food-related accents |

### Icon Categories

Based on the Figma VIS, icons are organized into these categories:

1. **Food & Ingredients** - vegetables, fruits, proteins, pantry items
2. **Kitchen Equipment** - pots, pans, utensils, appliances
3. **Operations** - documents, calendars, checklists, reports
4. **Actions** - upload, download, edit, create, delete
5. **Navigation** - arrows, menus, search, settings
6. **AI/Assistant** - sparkles, magic wand, brain, lightbulb (Galley Assist specific)

---

## Using Icons in Release Notes

### For Email HTML

When using icons in release notes, prefer:

1. **Emoji alternatives** - Simple, universal support
2. **Inline SVG** - For custom Galley icons (ensure brand colors)
3. **Image URLs** - Host on HubSpot or CDN

### Emoji Mapping (Fallback)

When custom icons aren't available, use these emoji alternatives that align with Galley's tone:

| Concept | Recommended Emoji | Avoid |
|---------|------------------|-------|
| Documents | 📄 | 📃 📜 |
| Spreadsheets | 📊 | 📈 📉 |
| Photos/Images | 📷 | 🖼️ 🎨 |
| Success/Check | ✓ (text) | ✅ 🎉 |
| Warning/Note | ⚠️ (sparingly) | 🚨 ❗ |
| Food/Recipe | 🍳 | Random food emoji |
| Time/Schedule | 📅 | ⏰ 🕐 |

**Important:** Use emojis sparingly. Prefer text labels or Galley's custom icons when possible.

---

## Creating New Icons

If you need to create icons that don't exist in the Figma library:

### Do's

- Match the hand-drawn, organic sketch style
- Use `#1A1A18` for all strokes
- Keep stroke weight consistent with existing icons
- Use rounded corners and soft edges
- Reference existing icons for proportions
- Keep icons simple and recognizable at small sizes

### Don'ts

- Don't use perfectly geometric shapes
- Don't use gradients in icons
- Don't use drop shadows
- Don't use colors outside the brand palette
- Don't create overly detailed or complex icons
- Don't use generic stock icon styles (flat, material, etc.)

---

## Quick Reference

### Brand Colors for Icons

```css
/* Stroke */
--icon-stroke: #1A1A18;

/* Fills */
--galley-green: #2F4F4F;
--sprout: #d4dfc8;
--dark-sprout: #9AB47E;

/* Background */
--icon-bg: #F3F6EF;
```

### Figma File Access

**Manual Access:**
1. Open [Galley VIS Figma File](https://www.figma.com/design/jBKuWmEGuoa68OKfOcS2PD/Galley_Irene-s-Work?node-id=5613-8569)
2. Navigate to the Iconography pages (pg 13-21)
3. Select desired icon
4. Export as SVG or copy to your design

**Programmatic Access (Figma MCP):**

Use the Figma MCP tools to look up icons:

```
# File Key and Node ID for Galley VIS
File Key: jBKuWmEGuoa68OKfOcS2PD
Node ID: 5613:8569 (main VIS section)

# Get metadata to search for icons
mcp__figma__get_metadata(fileKey: "jBKuWmEGuoa68OKfOcS2PD", nodeId: "5613:8569")

# Get screenshot of a specific icon
mcp__figma__get_screenshot(fileKey: "jBKuWmEGuoa68OKfOcS2PD", nodeId: "[icon-node-id]")

# Get design context for code generation
mcp__figma__get_design_context(fileKey: "jBKuWmEGuoa68OKfOcS2PD", nodeId: "[icon-node-id]")
```

**Icon Page Node IDs (approximate):**
- Iconography pages: Search within node `5613:8569`
- Look for frames named "Galley VIS_Iconography_pg X"
- Galley Assist icons: Look for frames named "Galley VIS_Galley Assist_Iconography_GA X"

### Exporting Icons

When exporting from Figma:
- **Format:** SVG preferred, PNG as fallback
- **Size:** Export at 1x, scale in CSS/HTML
- **Include:** Preserve stroke colors
- **Optimize:** Run through SVGO if needed

---

## Examples

### Icon Grid Section (HTML)

```html
<table width="100%" style="border-width: 0px;" role="presentation" cellspacing="0">
  <tr>
    <td style="background-color: #F3F6EF; border-radius: 8px; padding: 20px;">
      <table width="100%" role="presentation" cellspacing="0">
        <tr>
          <td style="text-align: center; padding: 10px;" width="33%">
            <div style="font-size: 24px; margin-bottom: 5px;">📄</div>
            <div style="color: #4D4D4D; font-family: 'Inter', sans-serif; font-size: 13px;">PDF, Word, Text</div>
          </td>
          <td style="text-align: center; padding: 10px;" width="33%">
            <div style="font-size: 24px; margin-bottom: 5px;">📊</div>
            <div style="color: #4D4D4D; font-family: 'Inter', sans-serif; font-size: 13px;">Excel, CSV</div>
          </td>
          <td style="text-align: center; padding: 10px;" width="33%">
            <div style="font-size: 24px; margin-bottom: 5px;">📷</div>
            <div style="color: #4D4D4D; font-family: 'Inter', sans-serif; font-size: 13px;">Photos & Images</div>
          </td>
        </tr>
      </table>
    </td>
  </tr>
</table>
```

---

*Last updated: January 2026*
*Based on Galley Visual Identity System V. 2025*
