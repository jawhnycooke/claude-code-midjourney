# Product Requirement Document: Video/Animation Prompt Support

**Created**: 2025-12-07
**Version**: 1.0
**Status**: Draft
**Complexity**: Medium
**Priority**: P1 (Should Have)

---

## Executive Summary

Add video/animation prompt support to the anime-mj plugin, enabling users to create animated content from their anime images using Midjourney's V1 video model. Features image-to-video workflows, camera motion controls, and full integration with existing anime-mj capabilities (artist styles, SREF codes, character references).

## Research Insights

**Midjourney V1 Video Model** (launched June 2025):
- Image-to-video workflow: Generate image first, then animate
- 5-second clips, extendable up to 21 seconds
- 480p (standard) or 720p (Pro/Mega plans)
- 24 FPS, no audio
- Web app only (not Discord bot)
- ~8x cost of image generation

**Key Parameters**:
- `--video`: Animate an image URL
- `--raw`: Reduce creative interpretation for precise motion control
- Motion levels: Low (subtle) vs High (dynamic/cinematic)
- Loop option: Start/end frame match for seamless loops

## Problem Statement

Users creating anime content with anime-mj currently have no guidance on animating their creations. Midjourney's V1 video model supports animation, but users need:
- Understanding of image-to-video workflow
- Motion prompt crafting for anime styles
- Integration with existing SREF/character reference workflows
- Camera motion guidance (pan, zoom, orbit)

## Target Users

### Primary Users
- Anime artists using anime-mj who want to animate their creations
- Content creators making animated anime clips for social media
- Users building consistent animated character content

### User Needs
- Seamless transition from image generation to animation
- Anime-appropriate motion styles (dramatic action, subtle slice-of-life)
- Maintain character/style consistency in animated output

## Goals & Success Criteria

### Product Goals
1. Enable users to animate anime-mj generated images
2. Provide anime-optimized motion prompt templates
3. Integrate video workflow with existing SREF/character reference features

### Success Criteria
- [ ] Plugin guides image-to-video workflow
- [ ] Motion prompt templates for anime genres (action, slice-of-life, etc.)
- [ ] Camera motion guidance (pan, zoom, orbit, static)
- [ ] Integration with existing artist styles and SREF codes
- [ ] Loop animation support documented
- [ ] Resolution/duration options explained

## Core Features

### Must Have (P0 - MVP)

1. **Image-to-Video Workflow Step**
   - Add Step 7: Animation (after character reference)
   - Ask if user wants to animate their image
   - Guide through motion prompt creation
   - Estimated effort: Low

2. **Motion Prompt Templates**
   - Action sequences (dynamic camera, speed lines effect)
   - Slice-of-life (subtle movement, gentle breeze)
   - Dramatic (slow zoom, emotional moments)
   - Combat (fast motion, impact frames)
   - Estimated effort: Medium

3. **Camera Motion Guide**
   - Pan (left/right/up/down)
   - Zoom (in/out, dramatic push)
   - Orbit (circular movement around subject)
   - Static (subtle character animation only)
   - Estimated effort: Low

4. **Parameter Documentation**
   - `--video` usage with image URL
   - `--raw` for precise control
   - Motion levels (low/high)
   - Loop options
   - Resolution options (480p/720p)
   - Estimated effort: Low

### Should Have (P1)

1. **Genre-Specific Motion Presets**
   - Shonen: High energy, dynamic camera
   - Seinen: Atmospheric, slow pans
   - Shoujo: Sparkle effects, soft focus
   - Mecha: Mechanical movement, transformations

2. **SREF + Video Integration**
   - Guidance on maintaining style in animated output
   - Which SREF codes work well with animation

### Nice to Have (P2)

1. **Storyboard Workflow**
   - Multi-shot animation sequences
   - Scene transition guidance

2. **Loop Animation Specialty**
   - Cinemagraph-style subtle loops
   - Perfect loop templates

## User Journey

### Primary Journey: Animate Existing Image

1. User generates anime image with `/anime-mj`
2. Plugin asks: "Would you like to animate this image?"
3. User selects animation style (action/subtle/dramatic/custom)
4. Plugin asks about camera motion preference
5. Plugin generates motion prompt with `--video` parameter
6. User copies prompt to Midjourney web app
7. User generates animation

### Secondary Journey: Plan for Animation

1. User invokes `/anime-mj` with animation intent
2. Plugin guides image creation optimized for animation
3. Image generated with animation-friendly composition
4. Seamless transition to animation workflow

## Technical Approach

### Architecture
Content extension to existing plugin files (same pattern as SREF/character consistency):
- `commands/anime-mj.md`: Add animation workflow step
- `skills/SKILL.md`: Add animation capability
- `docs/video-animation.md`: Full animation reference (NEW)
- `README.md`: Update features

### Integration Points
- Works with existing artist styles
- Compatible with SREF codes
- Works with character references (`--cref`)
- Respects aspect ratio choices

### Platform Limitation
**Important**: Video generation is web app only (not Discord bot). Plugin must clearly communicate this limitation.

## Constraints

### Technical Constraints
- Web app only (no Discord bot support)
- 5-21 second duration limit
- 480p/720p resolution only
- No audio in output
- Higher cost (~8x image generation)

### Scope Constraints
- Not building video editing features
- Not handling video-to-video
- Not supporting non-Midjourney video tools

## Out of Scope

- Video editing or post-processing guidance
- Audio/music synchronization
- Multi-clip video editing workflows
- Integration with external video tools
- Automated video generation (user must use web app)

## Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| MJ video features change | Medium | Document version, monitor updates |
| Web-only limitation frustrates users | Low | Clear communication upfront |
| Animation quality varies | Medium | Provide optimization tips |

## Open Questions

1. Should we include pricing/cost guidance?
2. Include troubleshooting for common animation issues?

## Next Steps

1. Review & approve this PRD
2. Run `/epcc-workflow:trd` to create technical requirements
3. Run `/epcc-workflow:epcc-code` to implement
4. Finalize with `/epcc-workflow:epcc-commit`

---

**End of PRD**
