# Product Requirement Document: Character Consistency Workflows

**Created**: 2025-12-07
**Version**: 1.0
**Status**: Draft
**Complexity**: Simple

---

## Executive Summary

Add character consistency workflow support to the anime-mj plugin, enabling users to create consistent characters across multiple images using Midjourney's `--cref` (Character Reference) and `--oref` (Omni Reference) parameters, plus reference sheet generation.

## Research Insights

**From [Midjourney Docs](https://docs.midjourney.com/hc/en-us/articles/32162917505293-Character-Reference)**:
- `--cref` analyzes facial features, hair, clothing style, and overall appearance
- `--cw` (character weight) ranges 0-100, default 100; lower values focus on face only
- Works best with Midjourney-generated source images

**From [AIarty Guide](https://www.aiarty.com/midjourney-guide/midjourney-consistent-character.htm)**:
- Reference sheets with multiple views (front, side, 3/4, expressions) provide maximum flexibility
- Single character, front-facing, good lighting = best source images
- Can chain multiple URLs: `--cref URL1 URL2`

**V7 Update**:
- `--oref` (Omni Reference) replaces `--cref` in V7
- Both still work but `--oref` is preferred for V7

## Problem Statement

Users want to maintain character consistency when generating multiple anime images (different poses, scenes, outfits), but the current plugin doesn't guide them through character reference workflows or help generate character sheets.

## Target Users

### Primary Users
- Anime artists creating character-focused content
- Content creators needing consistent characters across scenes
- Manga/webtoon creators building character designs

### Pain Points
- Characters look different in each generation
- Don't know how to use `--cref`/`--oref` effectively
- Need guidance on creating good reference sheets

## Goals & Success Criteria

### Product Goals
1. Guide users through character reference workflows
2. Help generate professional-quality reference sheets
3. Educate on `--cref`/`--cw`/`--oref` best practices

### Acceptance Criteria
- [ ] Plugin offers character reference sheet generation workflow
- [ ] Plugin explains `--cref` vs `--oref` usage
- [ ] Plugin guides `--cw` weight selection based on use case
- [ ] Example prompts for turntable/multi-view sheets included

## Core Features

### Must Have (P0 - MVP)

1. **Character Reference Sheet Generator**
   - Prompts for multi-view character sheets (front, side, 3/4, back)
   - Expression sheet prompts (happy, angry, sad, surprised)
   - Outfit variation prompts
   - Uses `--niji 6` with clean white background

2. **--cref Usage Guidance**
   - Step-by-step workflow: generate character → use as reference
   - Explain `--cw` values (100=full, 0=face only)
   - Tips for best source images

3. **V7 Compatibility**
   - Document `--oref` as V7 replacement
   - Provide both parameter options

### Should Have (P1)

4. **Multiple Character Handling**
   - Guide for chaining `--cref URL1 URL2`
   - Tips for multi-character scenes

## User Journey

### Primary Journey: Create Consistent Character

1. User invokes `/anime-mj` wanting a character in multiple scenes
2. Plugin asks: "Do you want to create a new character or use an existing reference?"
3. **New character path**:
   - Generate character reference sheet first
   - User uploads result to Discord
   - Plugin provides `--cref` prompt template with their description
4. **Existing reference path**:
   - Plugin asks for image URL
   - Plugin provides prompt with `--cref [URL]` appended
5. Plugin explains `--cw` options for outfit/pose changes

## Technical Approach

### Integration Points
- Add new workflow section to `anime-mj.md` command
- Add character reference content to `SKILL.md`
- No new files needed - extends existing command

### New Prompt Templates

**Reference Sheet Template:**
```
character reference sheet, [character description], multiple views, front view, side view, three-quarter view, back view, clean white background, full body, anime style --niji 6 --ar 16:9
```

**Expression Sheet Template:**
```
expression sheet, [character description], multiple expressions, happy, sad, angry, surprised, neutral, head shots, clean white background --niji 6 --ar 16:9
```

**Using Reference Template:**
```
[scene description], [character description] --niji 6 --cref [URL] --cw [weight] --ar [ratio]
```

## Out of Scope

- Real photo to anime character conversion (unreliable)
- Automatic URL handling (user must upload to Discord)
- Custom character database/storage

## Next Steps

This PRD feeds into the EPCC workflow:

1. Review & approve this PRD
2. Run `/epcc-plan` to create implementation plan
3. Begin development with `/epcc-code`
4. Finalize with `/epcc-commit`

---

**End of PRD**
