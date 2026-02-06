# GitHub Repository Setup Guide

> **How to populate and publish the WattNext Organizational Intelligence Knowledge Base**

This guide walks you through converting the 157 Q&As across 13 dimensions into the GitHub repository structure.

## What You Have

**Content Files Created:**
- 28 markdown files in `/mnt/outputs/` with blog posts, LinkedIn posts, Instagram carousels, and Q&As
- 157 total Q&A pieces mapped to 134 organizational indicators
- All content written in WattNext's sharp, behavioral voice

**What Needs To Happen:**
Convert these files into individual GitHub-formatted Q&A markdown files with proper frontmatter and structure.

## Repository Structure

```
github-repo/
├── README.md                    # Main navigation hub ✅
├── LICENSE.md                   # CC BY-NC-SA 4.0 ✅
├── CONTRIBUTING.md              # Contribution guidelines ✅
├── SETUP-GUIDE.md               # This file ✅
│
├── .github/
│   └── workflows/
│       ├── link-checker.yml     # Automated link checking ✅
│       └── link-check-config.json ✅
│
├── dimensions/
│   ├── strategic-alignment.md   # Dimension overview ✅ (sample)
│   ├── trust-integrity.md       # (need to create 12 more)
│   ├── organizational-culture.md
│   ├── vision-strategic-direction.md
│   ├── decision-making-quality.md
│   ├── cross-team-collaboration.md
│   ├── role-clarity-accountability.md
│   ├── support-for-teams.md
│   ├── resource-availability.md
│   ├── process-robustness.md
│   ├── knowledge-management.md
│   ├── operational-resilience.md
│   └── leadership-pipeline.md
│
└── questions/
    ├── INDEX.md                 # Complete question index ✅
    ├── alignment-vs-agreement.md ✅ (sample)
    └── [156 more Q&A files to create]
```

## Step 1: Extract Q&As From Existing Files

You have 13 dimension content packages. Each contains 5 canonical Q&As.

**Example from strategic-alignment-canonical-qas.md:**

Each Q&A currently looks like:
```markdown
## Q&A 1: What causes execution gaps between strategy and day-to-day work?

**Slug:** `what-causes-execution-gaps-between-strategy-and-day-to-day-work`
**Primary Topic:** Strategic Alignment
**Featured Snippet Potential:** High
**Voice Search Optimized:** Yes

---

### Short Answer
[content]

### Why This Matters
[content]
...
```

## Step 2: Convert To GitHub Format

Each Q&A needs its own file with frontmatter:

**Filename:** `questions/what-causes-execution-gaps.md`

**Content:**
```markdown
---
title: "What causes execution gaps between strategy and day-to-day work?"
dimension: Strategic Alignment
category: Diagnosis & Patterns
tags: [strategy-execution, alignment, leadership, systems]
difficulty: intermediate
reading_time: 6 min
seo_title: "Why Strategies Fail in Execution | WattNext"
meta_description: "Execution gaps occur when strategy remains aspirational. Learn the 5 system-level causes and how to fix them."
canonical_url: "https://wattnext.ai/insights/what-causes-execution-gaps"
related_indicators: [1, 4, 9, 10]
---

# What causes execution gaps between strategy and day-to-day work?

## Quick Answer

[Short answer section]

## Why This Matters

[Why this matters section]

[Rest of content...]

## Related Content

**Strategic Alignment:**
- [How do you translate strategy into operational behavior?](strategy-to-behavior.md)
- [Why do leadership teams think they're aligned when they're not?](leadership-alignment-illusion.md)

---

## Learn More

**Want to diagnose where your execution gaps exist?**
[Learn about ViVo Pulse](https://wattnext.ai/vivo-pulse)

---

*Part of the [WattNext Organizational Intelligence Knowledge Base](../README.md)*
*Dimension: [Strategic Alignment](../dimensions/strategic-alignment.md)*
```

## Step 3: Create All Dimension Overview Files

Each dimension needs an overview file like `dimensions/strategic-alignment.md` (sample provided).

**Template structure:**
1. **Overview** - What this dimension measures, why it matters
2. **What We Measure** - Number of indicators, broad categories
3. **Common Patterns** - 3-4 recurring patterns with system-level explanations
4. **Questions In This Dimension** - Organized by category
5. **Related Dimensions** - How it connects to other dimensions
6. **Research Foundation** - Theory and evidence base
7. **What Good Looks Like** - Behavioral indicators of health
8. **Diagnostic Approach** - How ViVo Pulse assesses this

Use `/mnt/outputs/strategic-alignment-blog.md` as source for patterns and insights.

## Step 4: Map Questions To Files

Use the spreadsheet `/mnt/outputs/wattnext-qa-indicator-mapping.xlsx` to:
- Get complete list of 157 questions
- Map each to its dimension
- Identify indicator numbers
- See which are gap-fills vs directly mapped

## Step 5: Add Metadata & Frontmatter

For each Q&A file, add:

**Frontmatter fields:**
```yaml
---
title: "Question as it appears in navigation"
dimension: Strategic Alignment | Trust & Integrity | etc
category: Foundational | Diagnosis | Translation | Systems | etc
tags: [relevant, keywords, for, search]
difficulty: foundational | intermediate | advanced
reading_time: 3-8 min
seo_title: "SEO-optimized title with keywords"
meta_description: "150-160 char description for search results"
canonical_url: "https://wattnext.ai/insights/slug"
related_indicators: [1, 4, 9] # from mapping spreadsheet
---
```

**Category guide:**
- **Foundational Understanding:** Core concepts, definitions, "what is X?"
- **Diagnosis & Patterns:** "Why does X happen?", pattern identification
- **Translation & Execution:** "How do you...?", operational implementation
- **Systems & Measurement:** Metrics, testing, systemic approaches
- **Scaling & Maintenance:** Growth, evolution, long-term sustainability

## Step 6: Cross-Reference Everything

Each Q&A should link to:
- **Related questions** in same dimension
- **Related questions** in connected dimensions
- **Dimension overview page**
- **Root README**

Use the "Related Content" section at bottom of each Q&A.

## Step 7: Quality Checks

Before publishing:

✅ **Structure:**
- [ ] Every Q&A has proper frontmatter
- [ ] Every dimension has overview file
- [ ] INDEX.md lists all 157 questions
- [ ] README.md provides clear navigation

✅ **Links:**
- [ ] All internal links use relative paths
- [ ] All external links use full URLs
- [ ] No broken links (use link-checker workflow)

✅ **Voice:**
- [ ] Sharp, behavioral, conversational tone
- [ ] System-level focus, not individual blame
- [ ] No HR jargon or consultant-speak
- [ ] Evidence-backed claims with citations

✅ **SEO:**
- [ ] Title tags optimized
- [ ] Meta descriptions 150-160 chars
- [ ] H1 matches page title
- [ ] H2/H3 hierarchy clear
- [ ] Keywords in first 100 words

## Automation Options

### Option 1: Manual Conversion
- Copy each Q&A into new file
- Add frontmatter manually
- Create cross-references
- **Time:** 20-30 hours for 157 files

### Option 2: Script-Based Conversion
- Write Python script to:
  - Parse existing markdown files
  - Extract Q&As
  - Generate frontmatter from mapping spreadsheet
  - Create files in correct structure
  - Add cross-references based on dimension relationships
- **Time:** 4-6 hours to build script + 1 hour to run + 4-6 hours QA

### Option 3: Hybrid Approach
- Script generates files with basic frontmatter
- Manual review and enhancement
- Add cross-references and related content
- **Time:** 6-8 hours build + 8-10 hours enhancement

**Recommendation:** Option 3 (Hybrid) balances efficiency with quality.

## Publishing Workflow

1. **Create GitHub repository**
   - Public or private (your choice)
   - Add README, LICENSE, CONTRIBUTING

2. **Populate content**
   - Add all dimension overviews
   - Add all Q&A files
   - Verify links work

3. **Enable GitHub Pages** (optional)
   - Settings → Pages
   - Source: main branch
   - Publishes to username.github.io/repo-name

4. **Set up CI/CD**
   - Link checker runs on push
   - Optional: Deploy to wattnext.ai/insights

5. **Announce**
   - Blog post about knowledge base launch
   - LinkedIn announcement
   - Link from main site

## Maintenance

**Weekly:**
- Review link checker results
- Fix any broken links

**Monthly:**
- Review new research for citation updates
- Consider new questions based on diagnostic patterns

**Quarterly:**
- Update statistics and research citations
- Review for clarity improvements
- Add real-world examples (anonymized)

## Next Steps

1. **Decide on approach:** Manual, scripted, or hybrid?
2. **Set timeline:** When does this need to be live?
3. **Assign resources:** Who's doing the conversion work?
4. **Quality standard:** What level of polish before v1.0?

## Questions?

Contact: support@wattnext.ai

---

*WattNext Knowledge Base Setup Guide*
*Created: February 2026*
