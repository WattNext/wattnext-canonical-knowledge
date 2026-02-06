# URL Structure Notes for Future Implementation

> **Current state:** All URLs point to `https://wattnext.ai` (main site)
> **Future state:** When blog and insights sections are built

## Planned URL Structure

When you build out the site sections, update these URL patterns in the repository:

### Blog Posts
**Pattern:** `https://wattnext.ai/blog/[slug]`

**Example:**
- Current: `canonical_url: "https://wattnext.ai"`
- Future: `canonical_url: "https://wattnext.ai/blog/alignment-vs-agreement"`

### Q&A / Insights
**Pattern:** `https://wattnext.ai/insights/[slug]`

**Example:**
- Current: `canonical_url: "https://wattnext.ai"`
- Future: `canonical_url: "https://wattnext.ai/insights/what-is-strategic-alignment"`

### Product Pages
**Pattern:** `https://wattnext.ai/vivo-pulse`

**Example:**
- Current: `[Learn about ViVo Pulse](https://wattnext.ai)`
- Future: `[Learn about ViVo Pulse](https://wattnext.ai/vivo-pulse)`

### Dimension Overviews
**Pattern:** `https://wattnext.ai/dimensions/[slug]`

**Example:**
- Current: Internal linking only
- Future: `https://wattnext.ai/dimensions/strategic-alignment`

## Files To Update When Sections Go Live

### 1. All Q&A Files (157 files in `questions/`)
Update frontmatter:
```yaml
canonical_url: "https://wattnext.ai/insights/[slug]"
```

### 2. All Dimension Files (13 files in `dimensions/`)
Update CTA links:
```markdown
[Learn about ViVo Pulse](https://wattnext.ai/vivo-pulse)
```

### 3. README.md
Update Contact section:
```markdown
- **Product:** [ViVo Pulse](https://wattnext.ai/vivo-pulse)
```

## Search & Replace Commands

When ready to update, use these patterns:

### Update Blog URLs
```bash
find questions/ -name "*.md" -exec sed -i 's|canonical_url: "https://wattnext.ai"|canonical_url: "https://wattnext.ai/insights/|g' {} \;
```

### Update ViVo Pulse Links
```bash
find . -name "*.md" -exec sed -i 's|\[Learn about ViVo Pulse\](https://wattnext.ai)|\[Learn about ViVo Pulse\](https://wattnext.ai/vivo-pulse)|g' {} \;
```

### Update Dimension Links (when sections are live)
```bash
find questions/ -name "*.md" -exec sed -i 's|\.\./dimensions/|\.\./dimensions/|g' {} \;
```

## Notes

- Keep all links pointing to `https://wattnext.ai` until the actual sections are built
- This prevents 404s from broken internal links
- When blog/insights sections go live, do a bulk update using the search/replace patterns above
- Test all links after update using the GitHub Actions link checker

## Current State (February 2026)

All URLs currently point to root:
- ✅ Main site: `https://wattnext.ai`
- ⏳ Blog section: Not yet built
- ⏳ Insights section: Not yet built
- ⏳ Product pages: Not yet built
- ⏳ Dimension pages: Not yet built

**Action:** Keep as-is until site structure is ready, then bulk update.

---

*This file is for internal reference only - not published with the knowledge base*
