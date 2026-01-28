# Release Notes Skill for Claude Code

A Claude Code skill that generates professional, brand-compliant HTML release notes with multiple template options.

## Features

- **4 Template Options**: Standard, Quick Update, Before & After, and Comprehensive
- Interactive template selection via Claude Code
- Brand-compliant HTML email templates
- Automatic codebase exploration to find permissions and navigation paths
- Icon guide with emoji fallbacks
- Consistent voice and tone guidelines
- Auto-generated filenames with date prefixes

## Templates

| Template | File | Best For |
|----------|------|----------|
| **Standard** | `template-standard.html` | Full feature announcements, new capabilities, how-to guides |
| **Quick Update** | `template-quick-update.html` | Bug fixes, minor improvements, patch notes, small enhancements |
| **Before & After** | `template-before-after.html` | Feature improvements, redesigns, UX enhancements, visual transformations |
| **Comprehensive** | `template-comprehensive.html` | Major launches, flagship features, detailed documentation, training materials |

### Template Details

#### Standard Template (Default)
Full-featured layout with all essential sections:
- Hero image with gradient header
- Step-by-step instructions
- Two-column feature lists
- Icon grid
- Callout box
- Requirements section
- Demo GIF slot

#### Quick Update Template
Minimal, scannable layout for small changes:
- Compact header with update type badge (Fix/Enhancement/Improvement)
- Checklist-style changes with checkmarks
- Optional quick tip box
- Streamlined footer

#### Before & After Template
Visual comparison-focused layout:
- "Before" section (gray, showing old pain points)
- "After" section (green, showing new benefits)
- Side-by-side image comparison slots
- Impact stats section (percentages, metrics)
- Transformation-focused narrative

#### Comprehensive Template
Most detailed, multi-section layout:
- Table of contents with anchor links
- Executive summary box
- Numbered feature cards with detailed descriptions
- Step-by-step instructions with individual images per step
- Video embed section
- FAQ section
- Requirements table
- Pro tips callout
- Related features grid
- Dual CTAs

## Installation

### Option 1: Clone to Your Project

Clone this repository into your project's root directory:

```bash
git clone https://github.com/galley-solutions/claude-code-release-notes-skill.git release-notes
```

Then copy the skill definition to your `.claude/skills` folder:

```bash
mkdir -p .claude/skills/release-notes
cp release-notes/.claude/skills/release-notes/SKILL.md .claude/skills/release-notes/
```

### Option 2: Manual Installation

1. **Download the repository** or copy the files manually

2. **Create the folder structure** in your project:

```
your-project/
├── .claude/
│   └── skills/
│       └── release-notes/
│           └── SKILL.md
└── release-notes/
    ├── templates/
    │   ├── template-standard.html
    │   ├── template-quick-update.html
    │   ├── template-before-after.html
    │   └── template-comprehensive.html
    ├── generated/           # Created automatically
    ├── ICON-GUIDE.md
    └── README.md
```

3. **Copy the files**:
   - Copy `SKILL.md` to `.claude/skills/release-notes/`
   - Copy `templates/`, `ICON-GUIDE.md` to `release-notes/`

## Configuration

### Customizing Templates

Edit the template files in `templates/` to match your brand:

1. **Colors**: Update the hex values in inline styles
2. **Logo**: Replace the logo URL in the footer
3. **Typography**: Modify font families and sizes
4. **Layout**: Add or remove sections as needed

### Customizing Brand Guidelines

Edit the SKILL.md file to update:

- Color palette
- Typography specifications
- Voice and tone guidelines
- Icon/emoji mappings

### Adding Figma Integration (Optional)

If you have a Figma design system, update `ICON-GUIDE.md` with:

1. Your Figma file key
2. Node IDs for icon pages
3. Instructions for using the Figma MCP

## Usage

### Basic Usage

In Claude Code, simply run:

```
/release-notes
```

Or with context:

```
/release-notes for the new user authentication feature
```

### What Happens

1. **Template Selection**: Claude asks which template to use:
   - Standard (Recommended) - Full layout for new features
   - Quick Update - Minimal, for bug fixes
   - Before & After - Visual comparison for improvements
   - Comprehensive - Extensive layout for major launches

2. **Codebase Research**: Claude explores your codebase to find:
   - How the feature works
   - Required permissions
   - Navigation paths

3. **Information Gathering**: Claude asks you about:
   - Feature title and tagline
   - Problem and solution
   - Step-by-step workflow
   - Key capabilities
   - CTA button details
   - Images/GIFs (optional)

4. **Generation**: Claude:
   - Reads the selected template
   - Fills in all placeholders
   - Saves to `generated/YYYY-MM-DD-feature-name.html`

5. **Preview**: Claude offers to open the file in your browser

### Example Output

Generated files are saved to `release-notes/generated/` with names like:

- `2026-01-27-user-authentication.html`
- `2026-01-28-bug-fixes.html`
- `2026-02-01-dashboard-redesign.html`

## File Structure

```
release-notes/
├── .claude/
│   └── skills/
│       └── release-notes/
│           └── SKILL.md              # Skill definition (copy to your project)
├── templates/
│   ├── template-standard.html        # Full feature announcements
│   ├── template-quick-update.html    # Bug fixes, minor updates
│   ├── template-before-after.html    # Improvements, redesigns
│   └── template-comprehensive.html   # Major launches, training docs
├── generated/                        # Output folder (auto-created)
│   └── .gitkeep
├── ICON-GUIDE.md                     # Icon and illustration reference
├── README.md                         # This file
└── .gitignore
```

## Template Sections Reference

### Standard Template Sections

| Section | Purpose |
|---------|---------|
| **Header** | Feature title and tagline with gradient background |
| **Intro** | Problem statement and solution overview |
| **How It Works** | Numbered step-by-step instructions |
| **Features List** | Two-column list of capabilities |
| **Icon Grid** | Visual representation of key concepts |
| **Callout Box** | Highlighted tip or important note |
| **Requirements** | Permissions and prerequisites |
| **CTA Button** | Call-to-action linking to the feature |
| **Footer** | Contact info and logo |

### Quick Update Template Sections

| Section | Purpose |
|---------|---------|
| **Compact Header** | Title with update type badge |
| **Changes List** | Checklist of what changed |
| **Quick Tip** | Optional helpful tip |
| **CTA Button** | Link to learn more |
| **Minimal Footer** | Simple logo and contact |

### Before & After Template Sections

| Section | Purpose |
|---------|---------|
| **Transformation Header** | Category and feature title |
| **Before Section** | Pain points with gray styling |
| **After Section** | Benefits with green styling |
| **Visual Comparison** | Side-by-side screenshots |
| **Impact Stats** | Metrics showing improvement |
| **How to Access** | Navigation instructions |
| **CTA Button** | Try it now link |

### Comprehensive Template Sections

| Section | Purpose |
|---------|---------|
| **Header** | Feature title with large hero image |
| **Table of Contents** | Anchor links to all sections |
| **Executive Summary** | Quick overview box |
| **Feature Cards** | Numbered detailed features |
| **Step-by-Step Guide** | Instructions with images |
| **Video Section** | Embedded video tutorial |
| **FAQ** | Common questions |
| **Requirements Table** | Permissions and prerequisites |
| **Pro Tips** | Expert callout box |
| **Related Features** | Grid of related items |
| **Dual CTAs** | Primary and secondary actions |

## Customization Examples

### Adding a New Section

Add HTML to any template:

```html
<!-- Custom Section -->
<h2 style="margin: 0 0 20px 0; color: #2F4F4F; font-family: 'Erode-Variable', 'Inter', sans-serif; font-size: 22px; font-weight: 700;">[Section Title]</h2>
<p style="margin: 0 0 25px 0; color: #4D4D4D; font-family: 'Inter', sans-serif; font-size: 15px; line-height: 1.6;">[Section content goes here]</p>
```

### Changing Colors

Update the color values in SKILL.md and template files:

```css
/* Primary color */
#2F4F4F → #YOUR_COLOR

/* Secondary/background */
#F3F6EF → #YOUR_BG_COLOR

/* Accent */
#d4dfc8 → #YOUR_ACCENT
```

### Adding Custom Icons

Update `ICON-GUIDE.md` with your icon mappings:

```markdown
| Concept | Emoji | Use Case |
|---------|-------|----------|
| Your Concept | 🎯 | Description |
```

## Troubleshooting

### Skill Not Found

Ensure the SKILL.md is in the correct location:

```
.claude/skills/release-notes/SKILL.md
```

### Template Not Found

The skill looks for templates at `release-notes/templates/`. Ensure this path exists relative to your workspace root.

### Generated Folder Missing

The skill will create the folder automatically, but you can create it manually:

```bash
mkdir -p release-notes/generated
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License - feel free to use and modify for your projects.
