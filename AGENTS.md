# AGENTS.md - Upasthiti Privacy Documentation

## Project Overview
This is a **documentation-only repository** hosting the privacy policy for the Vidya Vihaar QLD Upasthiti App - a student attendance tracking system that uses QR code scanning and Supabase backend.

**Key Context:**
- App Purpose: School attendance management with QR code check-in
- Backend: Supabase (secure data storage with encryption)
- Data Collected: Student names, attendance status, staff member names
- Deployment: Static site on GitHub Pages (automatic on main branch push)

## Repository Structure

```
upasthiti-privacy/
├── index.html            # Static HTML privacy policy (served as homepage)
├── README.md             # Markdown source (documentation reference)
├── index.md              # Deprecated markdown version (kept for reference)
├── .github/workflows/
│   └── static.yml        # Deployment workflow to GitHub Pages
└── AGENTS.md             # This file
```

**Important:** `index.html` is the primary served file. README.md and index.md are kept for documentation reference but are not served to users.

## Documentation Standards & Patterns

### Privacy Policy Structure
The privacy policy follows a 5-point framework (see both markdown files):
1. **Information Collection** - What data is gathered
2. **Camera Usage** - Specific mention of QR code scanning (no images stored)
3. **Data Usage** - Internal school management only
4. **Third-Party Sharing** - Clear "no sharing" statement
5. **Data Security** - Supabase encryption reference

**Pattern:** Always maintain this structure when updating. Each point is critical for compliance and user trust. Do not combine or reorder these sections.

### Markdown Conventions
- Use bold for section titles: `**Section Name**:`
- Single-level list format (numbered list for main policy points)
- Keep language simple and school-appropriate
- Link to external services only if necessary for transparency

## Critical Modification Rules

### Privacy Policy Updates
**Before any changes:**
1. Consult with legal/compliance team if adding/removing data collection points
2. Update `index.html` with new privacy policy content
3. Update `README.md` as documentation reference to match changes
4. Changes to data handling or third-party integrations require careful review
5. Preserve the 5-point structure - don't add custom sections

**Common Updates:**
- **Data retention period changes:** Update the Data Usage section in index.html
- **New service integrations:** Document in the Data Usage section
- **Security improvements:** Update the Data Security section with new details
- **HTML changes:** Ensure consistent styling and semantic HTML structure

### Deployment
- GitHub Actions workflow at `.github/workflows/static.yml` automatically deploys to GitHub Pages on every push to `main` branch
- No manual deploy needed - commits trigger automatic deployment
- Live site: Check GitHub Pages settings to find deployment URL
- Entire repository root (`.`) is uploaded as the static site

## Integration Points

### Upasthiti App Integration (Read-Only in This Repo)
This repo documents policies for:
- **QR Code Scanner:** Camera access mention - ensure accurate if app functionality changes
- **Supabase Backend:** Data encryption and storage - update "Data Security" if backend security changes
- **Staff/Student Data:** Mention in multiple sections - keep consistent with actual app data model

**Note:** This is documentation only. Actual app code exists in separate repository.

## Developer Workflows

### Updating Privacy Policy
```bash
# 1. Create branch
git checkout -b update/privacy-policy-<date>

# 2. Edit HTML content (keep 5-point structure):
# - index.html (primary served file)
# - README.md (optional - for reference)

# 3. Test locally - open index.html in browser to preview styling

# 4. Commit with descriptive message
git commit -m "update: privacy policy - [description of change]"

# 5. Push and automatic deployment triggers
git push origin update/privacy-policy-<date>
# GitHub Actions automatically deploys to GitHub Pages on merge to main
```

### Verification Checklist
- [ ] index.html updated with new content
- [ ] 5-point policy structure maintained
- [ ] HTML renders correctly in browser (test locally)
- [ ] No typos or grammatical errors
- [ ] Accurate references to data collection (aligns with app)
- [ ] Supabase security claims are current
- [ ] Updated README.md for documentation reference
- [ ] Push triggers automatic GitHub Pages deployment

## Key Files Reference

| File | Purpose |
|------|---------|
| index.html | Static HTML privacy policy (primary file served to users) |
| README.md | Markdown documentation & changelog reference |
| index.md | Deprecated markdown version (kept for reference only) |
| .github/workflows/static.yml | Auto-deployment to GitHub Pages |
| .gitignore | Empty (minimal repo) |
| AGENTS.md | AI agent guidance (this file) |

## Important Gotchas

1. **Primary File is index.html:** The HTML file is what users see. Any changes must be made to `index.html`, not markdown files. Markdown files are now for internal reference only.

2. **HTML Structure Matters:** Preserve the semantic HTML structure, especially the 5-point list structure inside `<ol>`. Styling changes should not affect the DOM structure.

3. **Preserve Policy Points:** Each of the 5 policy sections is wrapped in `<li class="policy-point">`. Keep this structure when updating content.

4. **Supabase Claims:** Any mention of Supabase security or features must match actual implementation. Outdated security claims reduce user trust.

5. **App Feature Alignment:** Camera usage and data collection descriptions must match current app behavior. If app adds new permissions, update the corresponding policy section in index.html.

6. **CSS Styling:** CSS is embedded in `<style>` tags within the HTML. Modify responsibly - changes affect the displayed policy appearance.

## Static HTML Deployment

This is pure static content with no build process required:
- `index.html` is the entry point served by GitHub Pages
- CSS is embedded in `<style>` tags (no external stylesheets)
- No JavaScript, no frameworks, no dependencies
- Just commit, push to `main`, and GitHub Actions automatically deploys
- GitHub Pages serves the entire repository root (`.`) as static files

