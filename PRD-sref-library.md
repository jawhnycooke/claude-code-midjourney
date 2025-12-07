# Product Requirement Document: SREF Code Library for Anime Styles

**Created**: 2025-12-07
**Version**: 1.0
**Status**: Draft
**Complexity**: Simple

---

## Executive Summary

Add a curated SREF (Style Reference) code library to the anime-mj plugin, featuring 30-50 hand-picked anime style codes plus guidance on discovering and using codes from external libraries.

## Research Insights

**From [sref-midjourney.com](https://sref-midjourney.com/)**:
- 5,539+ SREF codes available with dedicated niji and anime sections
- Codes produce consistent visual styles across generations

**From [Midlibrary.io](https://midlibrary.io/midguide/deep-dive-into-midjourney-sref-codes)**:
- 2,800+ hand-picked codes in 17 "flavors"
- Old V6 codes may not work identically in V7 (use `--sv 4` for compatibility)

**From [promptsref.com](https://promptsref.com/version/niji-6)**:
- Dedicated Niji 6 SREF collection available
- Codes can be blended: `--sref 123 456`
- `--sw` (style weight) controls influence: 0-1000, default 100

**Key Technical Notes**:
- SREF codes are random numeric identifiers
- Works with `--niji 6` when combined properly
- Multiple codes can be weighted differently

## Problem Statement

Users want to achieve specific anime visual styles consistently but don't know which SREF codes produce anime aesthetics compatible with Niji mode. External libraries are overwhelming with thousands of options.

## Target Users

### Primary Users
- Anime artists seeking consistent visual styles
- Users who want quick access to proven anime aesthetics
- Creators building cohesive art series

### Pain Points
- SREF libraries have thousands of codes without curation
- Hard to know which codes work well with Niji mode
- No guidance on combining/weighting codes

## Goals & Success Criteria

### Product Goals
1. Provide curated anime SREF codes that work with Niji
2. Teach users how SREF parameters work
3. Link to comprehensive external libraries for exploration

### Acceptance Criteria
- [ ] 30-50 curated anime SREF codes organized by style
- [ ] Each code has description and recommended use case
- [ ] `--sw` weight guidance included
- [ ] Links to external SREF libraries
- [ ] Examples of combining codes

## Core Features

### Must Have (P0 - MVP)

1. **Curated Anime SREF Library**
   - 30-50 codes organized by visual style:
     - **Ghibli/Soft**: Warm, nostalgic, nature-inspired
     - **Shonen/Dynamic**: Bold, action-oriented
     - **Seinen/Dark**: Moody, atmospheric, detailed
     - **Shoujo/Elegant**: Sparkles, soft lighting, romantic
     - **Retro**: 80s/90s anime aesthetic
     - **Modern/Clean**: Contemporary anime look
   - Each entry includes: code, style name, description, best use case

2. **SREF Parameter Education**
   - `--sref [code]` basic usage
   - `--sw [0-1000]` style weight explanation
   - Combining codes: `--sref 123 456`
   - Weighting codes: `--sref 123::2 456::1`

3. **External Library Links**
   - [sref-midjourney.com](https://sref-midjourney.com/style/niji) - 5,500+ codes
   - [Midlibrary.io](https://midlibrary.io/) - 2,800+ curated codes
   - [promptsref.com/niji-6](https://promptsref.com/version/niji-6) - Niji-specific collection

### Should Have (P1)

4. **Code Discovery Workflow**
   - How to find new codes (random generation)
   - Testing and saving favorites
   - V6 vs V7 compatibility notes

## Curated SREF Codes (Initial Set)

### Ghibli/Soft Style
| Code | Name | Description |
|------|------|-------------|
| 3408846050 | Ghibli Vibes | Studio Ghibli atmospheric quality |
| 918084796 | Anime Serenity | Peaceful, contemplative mood |
| 3161604773 | Pastel Garden | Soft colors, garden settings |
| 3573349435 | Gentle Pastel | Delicate emotional tones |
| 13015050 | Spring Melody | Nature-inspired, pastel |

### Dynamic/Action Style
| Code | Name | Description |
|------|------|-------------|
| 3730983883 | Dynamic Comic | Metallic, action-oriented |
| 910384726 | Vibrant Manga | Classic manga energy |
| 2063895279 | Cheerful Anime | Bright, energetic |

### Dark/Atmospheric Style
| Code | Name | Description |
|------|------|-------------|
| 416523183 | Anime Vampire | Dark, gothic styling |
| 2131889852 | Ethereal Fantasy | Magical, otherworldly |
| 3136260955 | Nostalgia Anime | Retro, moody |

### Modern/Stylized
| Code | Name | Description |
|------|------|-------------|
| 2178024008 | Futuristic Iridescence | Tech, shimmering effects |
| 200135 | Floral Elegance | Botanical, refined |

*Note: Full library will expand to 30-50 codes during implementation*

## User Journey

### Primary Journey: Apply Style to Prompt

1. User building anime prompt with `/anime-mj`
2. Plugin asks: "Would you like to apply a style reference?"
3. **Browse library path**:
   - Plugin shows categories (Ghibli, Dynamic, Dark, etc.)
   - User selects category
   - Plugin shows codes with descriptions
   - User picks code, plugin appends `--sref [code]`
4. **Custom code path**:
   - User provides their own SREF code
   - Plugin appends to prompt
5. Plugin asks about style weight (`--sw`)

## Technical Approach

### Integration Points
- Add SREF section to `anime-mj.md` command
- Add SREF content to `SKILL.md`
- Consider separate reference file for code library if too long

### Example Prompt Output
```
A samurai in cherry blossom forest, dramatic pose, Kentaro Miura style, dark fantasy --niji 6 --style expressive --ar 16:9 --sref 3408846050 --sw 250
```

## Out of Scope

- Automatic SREF code discovery/testing
- Personal SREF library storage
- Code rating/voting system

## Open Questions

- Should codes be in main command file or separate reference file?
- How many codes per category is optimal?

## Next Steps

This PRD feeds into the EPCC workflow:

1. Review & approve this PRD
2. Run `/epcc-plan` to create implementation plan
3. Begin development with `/epcc-code`
4. Finalize with `/epcc-commit`

---

**End of PRD**
