# Release Notes Skill Setup Instructions

This file contains instructions for Claude Code to set up the release-notes skill in your project.

## Quick Setup

Ask Claude Code to run this setup by saying:

```
Please read and follow the instructions in release-notes/SETUP.md to set up the /release-notes skill
```

---

## Setup Instructions for Claude

When asked to set up this skill, follow these steps:

### Step 1: Identify Paths

Determine the base paths:
- **REPO_ROOT**: The root directory of the user's project (where .claude folder should be)
- **SKILL_SOURCE**: The directory containing this SETUP.md file (release-notes skill source)

### Step 2: Create Folder Structure

Create the following directories if they don't exist:

```bash
mkdir -p {REPO_ROOT}/.claude/skills/release-notes
mkdir -p {REPO_ROOT}/release-notes/templates
mkdir -p {REPO_ROOT}/release-notes/generated
```

### Step 3: Copy Templates

Copy all template files from the source to the project:

```
{SKILL_SOURCE}/templates/template-standard.html      → {REPO_ROOT}/release-notes/templates/
{SKILL_SOURCE}/templates/template-quick-update.html  → {REPO_ROOT}/release-notes/templates/
{SKILL_SOURCE}/templates/template-before-after.html  → {REPO_ROOT}/release-notes/templates/
{SKILL_SOURCE}/templates/template-comprehensive.html → {REPO_ROOT}/release-notes/templates/
```

### Step 4: Copy Icon Guide

```
{SKILL_SOURCE}/ICON-GUIDE.md → {REPO_ROOT}/release-notes/ICON-GUIDE.md
```

### Step 5: Create the Skill Definition

Read the SKILL.md file from `{SKILL_SOURCE}/.claude/skills/release-notes/SKILL.md` and create a copy at `{REPO_ROOT}/.claude/skills/release-notes/SKILL.md`.

**IMPORTANT**: Replace all instances of `{RELEASE_NOTES_BASE}` with the actual path:
- Replace `{RELEASE_NOTES_BASE}` with `{REPO_ROOT}/release-notes`

### Step 6: Create .gitkeep

Create a .gitkeep file in the generated folder:

```bash
touch {REPO_ROOT}/release-notes/generated/.gitkeep
```

### Step 7: Verify Setup

Confirm the following structure exists:

```
{REPO_ROOT}/
├── .claude/
│   └── skills/
│       └── release-notes/
│           └── SKILL.md              ✓ Skill definition with correct paths
└── release-notes/
    ├── templates/
    │   ├── template-standard.html    ✓ Full feature template
    │   ├── template-quick-update.html ✓ Bug fix template
    │   ├── template-before-after.html ✓ Comparison template
    │   └── template-comprehensive.html ✓ Major launch template
    ├── generated/
    │   └── .gitkeep                  ✓ Output folder ready
    └── ICON-GUIDE.md                 ✓ Icon reference
```

### Step 8: Confirm to User

Tell the user:

> ✓ Release notes skill has been set up successfully!
>
> **To use it:** Type `/release-notes` followed by a description of your feature.
>
> **Example:** `/release-notes for the new bulk import feature`
>
> **Templates available:**
> - Standard - Full feature announcements
> - Quick Update - Bug fixes and minor updates
> - Before & After - Improvements and redesigns
> - Comprehensive - Major launches and training docs
>
> Generated release notes will be saved to: `release-notes/generated/`

---

## Customization (Optional)

After setup, the user can customize:

1. **Brand Colors**: Edit SKILL.md color palette section
2. **Templates**: Modify HTML in `release-notes/templates/`
3. **Icons**: Update `release-notes/ICON-GUIDE.md` with custom emoji mappings
4. **Figma Integration**: Add Figma file key and node IDs to ICON-GUIDE.md

---

## Troubleshooting

**Skill not appearing?**
- Ensure SKILL.md is at `.claude/skills/release-notes/SKILL.md`
- Check that the file has valid YAML frontmatter

**Templates not found?**
- Verify templates are in `release-notes/templates/`
- Check that paths in SKILL.md match your folder structure

**Permission errors?**
- Ensure you have write access to the project directory
