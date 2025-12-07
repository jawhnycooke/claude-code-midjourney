# Technical Requirements Document: SREF Code Library for Anime Styles

**Created**: 2025-12-07
**Version**: 1.0
**Complexity**: Simple
**PRD Reference**: PRD-sref-library.md

---

## Executive Summary

Add a curated SREF (Style Reference) code library to the anime-mj plugin. The library provides 30-50 hand-picked anime-optimized codes organized by visual style, plus educational content on SREF parameters and links to external libraries.

## Architecture

### Pattern
**Modular Content Addition** - Extending existing Claude Code plugin with new reference documentation and command workflow.

### Component Structure
```
plugins/anime-mj/
├── .claude-plugin/
│   └── plugin.json          # No changes needed
├── commands/
│   └── anime-mj.md          # Add SREF workflow step + top codes
├── skills/
│   └── SKILL.md             # Add SREF capability description
├── docs/                    # NEW FOLDER
│   ├── README.md            # Index of reference docs
│   └── sref-library.md      # Full curated SREF code library
└── README.md                # Update feature list
```

### Data Flow
1. User invokes `/anime-mj` command
2. After building prompt, user asked "Apply style reference?"
3. **Browse path**: Show categories → User picks → Append `--sref [code]`
4. **Custom path**: User provides own code → Append to prompt
5. Ask about `--sw` weight → Append `--sw [value]`

## Technology Stack

### File Format
**Markdown** - Native Claude Code plugin format, no external dependencies

### Content Organization
- **docs/sref-library.md**: Full library with 30-50 codes, 6 categories
- **commands/anime-mj.md**: Quick reference (top 10-15 codes inline)
- **skills/SKILL.md**: Capability description for autonomous activation

## Data Architecture

### SREF Code Categories
| Category | Target Count | Description |
|----------|--------------|-------------|
| Ghibli/Soft | 8-10 | Warm, nostalgic, nature-inspired |
| Shonen/Dynamic | 6-8 | Bold, action-oriented, energetic |
| Seinen/Dark | 6-8 | Moody, atmospheric, detailed |
| Shoujo/Elegant | 5-6 | Sparkles, soft lighting, romantic |
| Retro | 4-5 | 80s/90s anime aesthetic |
| Modern/Clean | 5-6 | Contemporary anime look |

**Total**: ~40-45 codes (varies by category as requested)

### Code Entry Schema
Each SREF code entry includes:
```markdown
| Code | Name | Description | Best For |
|------|------|-------------|----------|
| 3408846050 | Ghibli Vibes | Studio Ghibli atmospheric quality | Scenic landscapes, magical realism |
```

### External Library Links
- [sref-midjourney.com/style/niji](https://sref-midjourney.com/style/niji) - 5,500+ codes
- [Midlibrary.io](https://midlibrary.io/) - 2,800+ curated codes
- [promptsref.com/niji-6](https://promptsref.com/version/niji-6) - Niji-specific collection

## Integration Points

### Command Workflow Addition
New step in `anime-mj.md` after technical options:

```
### Step 5: Style Reference (Optional)

Ask: "Would you like to apply a style reference for consistent aesthetics?"
Options:
- Browse curated library (show style categories)
- Enter custom SREF code
- Skip (no style reference)

If selected:
- Present category → codes with descriptions
- Ask about --sw weight (100=default, higher=stronger influence)
```

### Parameter Education Section
Add to command file:
```markdown
## SREF Parameter Reference

| Parameter | Description |
|-----------|-------------|
| `--sref [code]` | Apply style reference code |
| `--sw [0-1000]` | Style weight (default 100) |
| `--sref 123 456` | Blend multiple codes |
| `--sref 123::2 456::1` | Weighted blend |
```

### V6/V7 Compatibility Notes
- Old V6 codes may look different in V7
- Add `--sv 4` to use old V7 model for code compatibility
- Niji 6 codes generally stable

## Files Created/Modified

### New Files
| File | Purpose |
|------|---------|
| `plugins/anime-mj/docs/README.md` | Index of reference documentation |
| `plugins/anime-mj/docs/sref-library.md` | Full curated SREF code library |

### Modified Files
| File | Changes |
|------|---------|
| `plugins/anime-mj/commands/anime-mj.md` | Add Step 5 SREF workflow, inline top codes, parameter reference |
| `plugins/anime-mj/skills/SKILL.md` | Add SREF capability to skill description |
| `plugins/anime-mj/README.md` | Update feature list to include SREF library |

## Implementation Status

### Completed
- [x] Create `plugins/anime-mj/docs/` directory
- [x] Create `docs/README.md` with index
- [x] Create `docs/sref-library.md` with full code library (40+ codes in 6 categories)
- [x] Add SREF workflow step to `anime-mj.md` command
- [x] Add inline quick reference (10 top codes)
- [x] Add SREF parameter documentation
- [x] Update `SKILL.md` with SREF capability
- [x] Update `README.md` feature list

## Example Output

```
A samurai in cherry blossom forest, dramatic pose, Kentaro Miura style, dark fantasy --niji 6 --style expressive --ar 16:9 --sref 3408846050 --sw 250
```

## Out of Scope

- Automatic SREF code discovery/testing
- Personal SREF library storage
- Code rating/voting system
- V7 `--sv` model switching automation

## Success Criteria

- [x] 40+ curated codes organized in 6 categories
- [x] Each code has name, description, and "best for" use case
- [x] SREF parameter education included
- [x] External library links provided
- [x] Command workflow includes SREF step
- [x] Examples of combining/weighting codes

---

**End of TRD**
