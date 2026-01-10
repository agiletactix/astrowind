# Claude Code Repository Setup Checklist

Use this checklist when cloning/setting up any repository to ensure everything works before making changes.

## 1. Initial Repository Setup

- [ ] Clone repository or checkout branch
- [ ] Verify working directory is correct (`pwd`)
- [ ] Check project type (package.json, requirements.txt, etc.)

## 2. Dependency Installation

### Node.js Projects
- [ ] Run `npm install` (or yarn/pnpm)
- [ ] Verify `node_modules` exists
- [ ] Check for any installation errors

### Python Projects
- [ ] Create virtual environment if needed
- [ ] Run `pip install -r requirements.txt`
- [ ] Verify dependencies installed

### Other Languages
- [ ] Ruby: `bundle install`
- [ ] Go: `go mod download`
- [ ] Rust: `cargo build`

## 3. Build Verification

- [ ] Run build command (`npm run build`, etc.)
- [ ] Check for build errors
- [ ] Verify output directory exists (`dist/`, `build/`, etc.)
- [ ] Check build logs for warnings

## 4. Development Server Test

- [ ] Start dev server (`npm run dev`, etc.)
- [ ] Verify server starts without errors
- [ ] Check that port is accessible
- [ ] Test hot-reload if applicable

## 5. Image Asset Quality Checks

When working with images (logos, hero images, etc.):

- [ ] Check actual image dimensions using `file` command
  ```bash
  file path/to/image.png
  ```
- [ ] Verify Image component width/height matches actual dimensions
- [ ] Set `quality="max"` or appropriate quality setting
- [ ] Test on retina/high-DPI displays
- [ ] Verify images aren't blurry or pixelated
- [ ] Check image file sizes (optimize if > 500KB)
- [ ] Ensure proper format (PNG for logos, WebP/JPEG for photos)

## 6. Git Configuration Check

- [ ] Verify correct branch
- [ ] Check git remote URLs
- [ ] Ensure branch name follows conventions (starts with `claude/` if required)
- [ ] Pull latest changes if branch exists remotely

## 7. Environment Variables

- [ ] Check for `.env.example` or `.env.sample`
- [ ] Create `.env` file if needed
- [ ] Verify all required env vars are set
- [ ] Check for API keys or secrets needed

## 8. Configuration Files

- [ ] Review main config files (astro.config.ts, next.config.js, etc.)
- [ ] Verify site URL and base path for deployments
- [ ] Check build output settings
- [ ] Review any custom configuration

## 9. Only THEN Start Editing

After ALL above checks pass:
- [ ] Make content/code changes
- [ ] Test changes locally
- [ ] Run build again to verify no breakage
- [ ] Commit with clear message
- [ ] Push to remote

## Common Gotchas

### Images
- ❌ Wrong dimensions cause blurriness
- ❌ File name case sensitivity (Linux vs Mac/Windows)
- ❌ Missing image optimization settings
- ✅ Always check actual dimensions first
- ✅ Use quality="max" for logos/crisp graphics

### Builds
- ❌ Skipping `npm install` causes module errors
- ❌ Missing environment variables cause build failures
- ❌ Wrong Node version causes compatibility issues
- ✅ Always verify clean build before editing
- ✅ Check build logs for warnings

### Git
- ❌ Pushing to wrong branch
- ❌ Branch naming conventions not followed
- ❌ Not pulling latest changes first
- ✅ Verify branch name matches requirements
- ✅ Always pull before push if branch exists

## Emergency Recovery

If something breaks:
1. Check git status
2. Review recent changes: `git diff`
3. Revert if needed: `git checkout -- file`
4. Re-run build to identify error
5. Check error logs carefully

## Notes

- This checklist is project-agnostic
- Adapt as needed for specific project types
- Update this file as new patterns emerge
- Keep in `.claude/` directory for easy reference
