# Technical Requirements Document: Video/Animation Prompt Support

**Created**: 2025-12-07
**Version**: 1.0
**Complexity**: Simple
**PRD Reference**: PRD-video-animation.md

---

## Executive Summary

Add video/animation workflow support to the anime-mj plugin, enabling users to animate their anime images using Midjourney's V1 video model. Features image-to-video workflows, motion prompt templates, camera motion guides, and integration with existing SREF/character reference features.

## Architecture

### Pattern
**Content Extension** - Adding workflow sections and templates to existing Claude Code plugin files. Same pattern used for SREF library and character consistency features.

### Component Structure
```
plugins/anime-mj/
├── commands/
│   └── anime-mj.md          # Add Step 7: Animation workflow
├── skills/
│   └── SKILL.md             # Add animation capability
├── docs/
│   ├── README.md            # Update index
│   └── video-animation.md   # NEW: Full animation reference
└── README.md                # Update feature list
```

### Data Flow
1. User invokes `/anime-mj` and generates image prompt
2. After image prompt built, plugin asks: "Would you like to animate this image?"
3. **If yes**: Guide through animation workflow
   - Select motion style (action/subtle/dramatic/custom)
   - Choose camera motion (pan/zoom/orbit/static)
   - Set motion level (low/high)
   - Optional: Loop animation
4. Plugin generates motion prompt with `--video` parameter
5. User copies to Midjourney **web app** (not Discord)

## Technology Stack

### File Format
**Markdown** - Native Claude Code plugin format, no external dependencies

### Content Organization
- **commands/anime-mj.md**: Animation workflow step + quick reference
- **skills/SKILL.md**: Animation capability for autonomous activation
- **docs/video-animation.md**: Full motion templates and parameter reference

## Integration Points

### New Workflow Step (Step 7: Animation)

```markdown
### Step 7: Animation (Optional)

Ask: "Would you like to animate this image?"
Options:
- Yes, animate it (proceed to animation workflow)
- No, image only (skip to final output)

**If Yes:**
1. Select motion style
2. Choose camera motion
3. Set motion level
4. Generate animation prompt
```

### Motion Style Templates

| Style | Description | Motion Level | Camera |
|-------|-------------|--------------|--------|
| Action | Dynamic movement, speed effects | High | Dynamic pan/zoom |
| Slice-of-life | Gentle breeze, subtle movement | Low | Static or slow pan |
| Dramatic | Emotional moments, cinematic | Medium | Slow zoom |
| Combat | Fast action, impact frames | High | Quick cuts, shake |

### Camera Motion Guide

| Motion | Prompt Keywords | Best For |
|--------|-----------------|----------|
| Pan Left/Right | "camera pans left", "horizontal tracking" | Following movement |
| Pan Up/Down | "camera tilts up", "vertical pan" | Revealing scenes |
| Zoom In | "camera pushes in", "zoom to face" | Emotional emphasis |
| Zoom Out | "camera pulls back", "wide reveal" | Scene establishing |
| Orbit | "camera orbits around", "360 rotation" | Character showcase |
| Static | "subtle movement", "breathing motion" | Cinemagraph style |

### Video Parameters Reference

| Parameter | Description | Values |
|-----------|-------------|--------|
| `--video` | Enable video generation | Required with image URL |
| `--raw` | Reduce AI interpretation | For precise control |
| Motion Level | Movement intensity | Low (subtle) / High (dynamic) |
| Loop | Seamless loop animation | Start/end frame match |
| Resolution | Output quality | 480p (Standard) / 720p (Pro/Mega) |
| Duration | Video length | 5 seconds (extendable to 21s) |

### Genre-Specific Motion Presets

| Genre | Motion Style | Camera | Keywords |
|-------|--------------|--------|----------|
| Shonen | High energy | Dynamic tracking | "action lines", "impact frames", "dynamic movement" |
| Seinen | Atmospheric | Slow pan | "subtle motion", "atmospheric", "cinematic" |
| Shoujo | Soft, sparkly | Gentle zoom | "sparkle effects", "soft focus", "flowing hair" |
| Slice of Life | Natural | Static/slow | "gentle breeze", "natural movement", "peaceful" |
| Mecha | Mechanical | Orbit/pan | "mechanical movement", "transformation", "precise motion" |
| Horror | Unsettling | Slow zoom | "creeping motion", "subtle unease", "shadows moving" |

### Platform Limitation Notice

**IMPORTANT**: Video generation is **web app only** - not available via Discord bot.

Include this notice in animation workflow:
```
⚠️ Note: Animation requires Midjourney web app (midjourney.com)
Discord bot does not support video generation.
```

## Files to Modify

| File | Changes |
|------|---------|
| `plugins/anime-mj/commands/anime-mj.md` | Add Step 7 animation workflow, motion templates, parameter guide |
| `plugins/anime-mj/skills/SKILL.md` | Add animation activation triggers and capability |
| `plugins/anime-mj/docs/README.md` | Add video-animation.md to index |
| `plugins/anime-mj/docs/video-animation.md` | NEW: Full animation reference |
| `plugins/anime-mj/README.md` | Update feature list, add animation section |

## Implementation Plan

### Phase 1: Create docs reference
1. Create `docs/video-animation.md` with full animation reference
2. Update `docs/README.md` index

### Phase 2: Update command file
1. Add Step 7: Animation workflow (after character reference)
2. Add motion style quick reference
3. Add camera motion guide
4. Add video parameters table
5. Add platform limitation notice
6. Add example prompts with `--video`

### Phase 3: Update skill and README
1. Update SKILL.md with animation triggers
2. Update README.md feature list and examples

## Example Outputs

### Action Animation
```
[Image URL] camera tracking shot following the warrior, dynamic movement, action lines, high motion --video
```

### Slice-of-Life Animation
```
[Image URL] gentle breeze, hair flowing softly, subtle movement, peaceful atmosphere, low motion --video --raw
```

### Dramatic Zoom
```
[Image URL] slow camera push in to face, emotional moment, cinematic, medium motion --video
```

### Loop Animation
```
[Image URL] seamless loop, gentle breathing motion, hair swaying, subtle movement --video loop
```

### With Character Reference
```
[Image URL] character walking forward, smooth motion --video --cref [ref URL] --cw 100
```

## Out of Scope

- Video editing or post-processing guidance
- Audio/music synchronization
- Multi-clip editing workflows
- Pricing/cost information (may change)
- Troubleshooting guides
- Non-Midjourney video tools

## Success Criteria

- [x] Plugin guides image-to-video workflow (Step 7)
- [x] Motion style templates for anime genres
- [x] Camera motion guide (pan, zoom, orbit, static)
- [x] Video parameter documentation (`--video`, `--raw`, motion levels)
- [x] Genre-specific motion presets
- [x] Loop animation support documented
- [x] Platform limitation clearly communicated
- [x] Integration with existing SREF/character reference features
- [x] Example prompts for each motion style

## PRD Alignment

**Features Supported**:
- Image-to-Video Workflow → Step 7 in command
- Motion Prompt Templates → Genre-specific presets
- Camera Motion Guide → Full reference table
- Parameter Documentation → Video parameters table

**Decisions from PRD**:
- Full integration with existing features (SREF, --cref)
- Web app only limitation prominently displayed
- No pricing info (per user preference)
- No troubleshooting section (keep focused)

## Next Steps

1. Review & approve this TRD
2. Run `/epcc-workflow:epcc-code` to implement
3. Finalize with `/epcc-workflow:epcc-commit`

---

**End of TRD**
