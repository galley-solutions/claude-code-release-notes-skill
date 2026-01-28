---
name: release-notes
description: Create a new release note for a feature or update. Uses the brand-compliant template and saves to the release-notes folder.
---

# Create Release Note

You are creating a release note using the brand-compliant HTML template.

## Important: Determine Base Path

Before doing anything else, determine the base path for this skill's files:

1. Look for the `release-notes` folder in the workspace root
2. If not found, search for a folder containing `templates/template-standard.html`
3. Store this path as `RELEASE_NOTES_BASE` for use throughout this skill

## Template Selection

Templates are located at: `{RELEASE_NOTES_BASE}/templates/`

### Available Templates

| Template | File | Best For |
|----------|------|----------|
| **Standard** | `template-standard.html` | Full feature announcements, new capabilities, how-to guides |
| **Quick Update** | `template-quick-update.html` | Bug fixes, minor improvements, patch notes, small enhancements |
| **Before & After** | `template-before-after.html` | Feature improvements, redesigns, UX enhancements, visual transformations |
| **Comprehensive** | `template-comprehensive.html` | Major launches, flagship features, detailed documentation, training materials |

### Template Descriptions

**1. Standard Template** (Default)
- Full-featured layout with all sections
- Hero image, step-by-step instructions, feature lists, icon grid
- Callout box, requirements section, demo GIF
- Best for: Feature launches, detailed documentation

**2. Quick Update Template**
- Minimal, scannable layout
- Compact header with update type badge (Fix/Enhancement/Improvement)
- Checklist-style changes with checkmarks
- Optional quick tip box
- Best for: Bug fixes, small improvements, patch releases

**3. Before & After Template**
- Visual comparison-focused layout
- "Before" section (gray, showing old pain points)
- "After" section (green, showing new benefits)
- Side-by-side image comparison slots
- Impact stats section (percentages, metrics)
- Best for: Redesigns, workflow improvements, UX updates

**4. Comprehensive Template**
- Most detailed, multi-section layout
- Table of contents, executive summary box
- Numbered feature cards with detailed descriptions
- Step-by-step instructions with individual images per step
- Video embed section, FAQ section
- Requirements table, pro tips callout
- Related features grid, dual CTAs
- Best for: Major product launches, flagship features, training materials

### Step: Ask User for Template Choice

**IMPORTANT: Before any other steps, use `AskUserQuestion` to ask which template to use.**

Use this exact question format:

```
AskUserQuestion with:
- question: "Which template would you like to use for this release note?"
- header: "Template"
- options:
  1. label: "Standard (Recommended)"
     description: "Full layout with hero image, steps, feature lists, callout box, demo GIF. Best for new features."
  2. label: "Quick Update"
     description: "Minimal layout with checklist of changes. Best for bug fixes and small improvements."
  3. label: "Before & After"
     description: "Visual comparison with before/after sections and metrics. Best for improvements and redesigns."
  4. label: "Comprehensive"
     description: "Extensive layout with TOC, FAQ, video section, and detailed feature cards. Best for major launches."
```

Based on the user's choice, use the corresponding template file:
- **Standard** → `template-standard.html`
- **Quick Update** → `template-quick-update.html`
- **Before & After** → `template-before-after.html`
- **Comprehensive** → `template-comprehensive.html`

## Brand Guidelines

All release notes must follow the brand guidelines defined in this skill.

### Color Palette

| Color | Hex | RGB | Usage |
|-------|-----|-----|-------|
| **Primary Green** | `#2F4F4F` | 47, 79, 79 | Headers, buttons, accents, headings |
| **Sprout** | `#d4dfc8` | 212, 223, 200 | Callout backgrounds, borders |
| **Dark Sprout** | `#9AB47E` | 154, 180, 126 | Accent borders |
| **TEXT** | `#4D4D4D` | 77, 77, 77 | All body text |
| **Icon Stroke** | `#1A1A18` | 26, 26, 24 | Icon outlines |
| **Page Background** | `#F3F6EF` | - | Page/section backgrounds |

### Typography

| Element | Font Family | Weight | Size |
|---------|-------------|--------|------|
| **Headings** | `'Erode-Variable', 'Inter', sans-serif` | 700 | 22px (h2), 18px (h3), 28px (h1) |
| **Body Text** | `'Inter', sans-serif` | 400 | 15px |
| **Buttons** | `'Inter', sans-serif` | 600 | 16px |

### Component Styling

- **Header**: Gradient from `#2F4F4F` to `#3D6363`
- **Feature boxes**: Background `#F3F6EF`, left border `#2F4F4F`
- **Callout boxes**: Background `#d4dfc8` (Sprout), border `#9AB47E` (Dark Sprout)
- **CTA buttons**: Background `#2F4F4F`, white text
- **Footer**: Background `#F3F6EF`, border `#d4dfc8`

### Colors to AVOID

Do not use these off-brand colors:
- Generic grays: `#f5f5f5`, `#fafafa`, `#f8f8f8`, `#666666`, `#888888`, `#999999`
- Off-brand greens: `#2d5a27`, `#4a7c43`, `#f8faf8`
- Yellow callouts: `#fff9e6`, `#f0e6c0`, `#8b6914`
- Generic borders: `#eeeeee`, `#E0E5DB`

### Icons & Illustrations

**Icon Guide:** `{RELEASE_NOTES_BASE}/ICON-GUIDE.md`

Read the icon guide before creating release notes. It contains:
- Icon style guidelines
- Emoji fallback mapping
- Figma references (if configured)

**Emoji fallbacks (use when custom icons unavailable):**

| Concept | Emoji | Use Case |
|---------|-------|----------|
| Documents | 📄 | PDF, Word, Text files |
| Spreadsheets | 📊 | Excel, CSV files |
| Photos | 📷 | Images, screenshots |
| Food/Recipe | 🍳 | Culinary content |
| Time/Schedule | 📅 | Dates, calendars |
| Location | 📍 | Places, venues |
| Search | 🔍 | Search functionality |
| Filter | 🔽 | Filtering options |
| Settings | ⚙️ | Configuration |
| Check/Success | ✓ | Completion (use text, not emoji) |

## Step 0: Research the Feature (BEFORE gathering information)

Before asking the user questions, research the feature in the codebase:

### 0.1 Explore the Feature
Use the `Task` tool with `subagent_type=Explore` to understand:
- How the feature works technically
- What components/pages are involved
- What GraphQL queries/mutations are used

### 0.2 Find Permissions
Search the codebase for permission checks related to the feature:

1. Search for permission patterns like `can[A-Z][a-zA-Z]+`
2. Check for authorization context usage
3. Look for permission-gated UI

**If permissions are found:** Include them in the release note automatically.
**If permissions are NOT found:** Ask the user what permissions are required.

### 0.3 Identify Navigation Path
From the codebase exploration, identify:
- The route/URL for the feature
- The sidebar icon/menu item
- Any tabs or sub-navigation

### 0.4 Read the Icon Guide
```
Read("{RELEASE_NOTES_BASE}/ICON-GUIDE.md")
```

## Step 1: Gather Information

Use the `AskUserQuestion` tool to gather the following information.

**Note:** Skip questions for information already discovered in Step 0.

### Required Information:

1. **Feature Title** - A clear, compelling title for the release note
2. **Tagline** - A short subtitle (one line)
3. **Problem Statement** - What problem does this feature solve?
4. **Solution Overview** - How does the feature solve the problem?
5. **How It Works** - Step-by-step process (3-5 steps)
6. **Key Features/Capabilities** - List of what the feature includes
7. **Permissions/Requirements** - (Only ask if not found in Step 0)
8. **Navigation Path** - (Only ask if not found in Step 0)
9. **CTA Button Text and Link** - What should the button say and where should it link?
10. **Images/GIFs** - URLs for hero image and demo GIF (optional)
11. **Special Callout** - Any important tip to highlight (optional)

## Step 2: Generate the Release Note

Read the selected template file and fill in all the placeholders:

1. Replace `[Feature Title Goes Here]` with the feature title
2. Replace `[Tagline or subtitle]` with the tagline
3. Fill in the intro paragraphs with problem/solution content
4. Populate the "How It Works" steps
5. Fill in the feature lists
6. Apply icons from ICON-GUIDE.md
7. Add the callout box content if provided
8. Set the permissions/requirements section
9. Add the navigation instructions
10. Set the CTA button text and link
11. Insert image/GIF URLs if provided (or add placeholders)

### Voice & Tone Guidelines

**Voice:**
- Be empathetic—never sterile or robotic
- Sound confident, grounded, and calm—not salesy or hype-driven
- Use clear, conversational language suitable for business contexts
- Avoid exaggerated enthusiasm or "AI-ish" filler
- Favor clarity over cleverness, but allow light warmth when appropriate

**Style:**
- Prefer concise sentences with natural variation in length
- Use concrete examples whenever possible
- Avoid vague claims like "revolutionary," "cutting-edge," or "game-changing"
- Write like a thoughtful colleague, not a marketer

**Content Guidelines:**
- **Length**: Keep paragraphs concise - 2-3 sentences max
- **Focus**: Benefits over features - explain WHY this matters to users

## Step 3: Determine Filename

The filename should follow this pattern:
`YYYY-MM-DD-feature-name.html`

- Use today's date
- Use lowercase kebab-case for the feature name
- Examples:
  - `2026-01-19-ai-menu-import.html`
  - `2026-01-22-inventory-dashboard.html`

## Step 4: Save the Release Note

**IMPORTANT:** Before saving, ensure the generated folder exists:

```bash
mkdir -p {RELEASE_NOTES_BASE}/generated
```

Save the completed HTML file to:
`{RELEASE_NOTES_BASE}/generated/[filename].html`

**Folder Structure:**
```
release-notes/
├── templates/
│   ├── template-standard.html       # Full feature announcements
│   ├── template-quick-update.html   # Bug fixes, minor updates
│   ├── template-before-after.html   # Improvements, redesigns
│   └── template-comprehensive.html  # Major launches, training docs
├── ICON-GUIDE.md                    # Icon reference guide
└── generated/                       # All generated release notes go here
    └── ...
```

## Step 5: Confirm and Preview

1. Tell the user the file has been created and provide the path
2. Offer to open it in the default browser:
   - macOS: `open [filepath]`
   - Linux: `xdg-open [filepath]`
   - Windows: `start [filepath]`

## Example Conversation Flow

**User**: `/release-notes` for the new bulk import feature

**Claude**: I'll help you create a release note for the bulk import feature.

*First, uses AskUserQuestion to ask which template:*
- Standard (Recommended) - Full layout for new features
- Quick Update - Minimal, for bug fixes
- Before & After - Visual comparison for improvements
- Comprehensive - Extensive layout for major launches

**User**: *Selects "Standard"*

**Claude**: Great choice! Let me gather some details about the feature.

*Uses AskUserQuestion to ask about:*
- Feature title and tagline
- Problem it solves
- How it works (steps)
- Key capabilities
- Any images or GIFs
- Permissions needed
- Navigation path

**User**: *Provides answers*

**Claude**: *Fills in the template, saves the file*

Great! I've created your release note at `release-notes/generated/2026-01-22-bulk-import.html`. Would you like me to open it in your browser to preview?
