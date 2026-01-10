# Claude Code Configuration

This directory contains configuration and checklists for working with Claude Code on this repository.

## Files

### `setup-checklist.md`
Comprehensive checklist for repository setup and common gotchas.

**Use this at the start of EVERY new Claude Code session** to ensure:
- Dependencies are installed
- Builds work before editing
- Images are properly configured
- No common mistakes are made

## How to Use in Future Chats

When starting a new Claude Code session, reference this checklist:

```
"Before we start, please follow the checklist in .claude/setup-checklist.md"
```

Or simply:

```
"Follow the setup checklist first"
```

## Why This Exists

This prevents common issues:
- ❌ Editing files before verifying build works
- ❌ Blurry images from wrong dimensions
- ❌ Missing dependencies causing failures
- ❌ Pushing to wrong branches

## Customization

Feel free to edit `setup-checklist.md` to add project-specific requirements or remove irrelevant sections.

## Making This Global

To use this checklist across multiple projects:

1. **Create a global template:**
   ```bash
   mkdir -p ~/.claude-templates
   cp .claude/setup-checklist.md ~/.claude-templates/
   ```

2. **Reference in any chat:**
   ```
   "Follow the checklist at ~/.claude-templates/setup-checklist.md"
   ```

3. **Or create a startup hook** (if using Claude Code CLI):
   Add to your shell profile:
   ```bash
   alias claude-setup="cat ~/.claude-templates/setup-checklist.md"
   ```

## Project-Specific Notes

### AgileTactix Astrowind Site

- **Logos:** Must be 1000x250px for crisp rendering
- **Base path:** `/astrowind` for GitHub Pages
- **Branch naming:** Must start with `claude/`
- **Circle community:** https://community.agiletactix.ai/
