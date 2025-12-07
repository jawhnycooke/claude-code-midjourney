# Video/Animation Reference Guide

Comprehensive guide to animating anime images using Midjourney's V1 video model.

> **Important**: Video generation is available on the **Midjourney web app only** (midjourney.com). Discord bot does not support video generation.

## Overview

Midjourney's V1 video model transforms still images into animated clips. The workflow is **image-to-video**: generate your anime image first, then animate it.

### Video Specifications

| Spec | Value |
|------|-------|
| Duration | 5 seconds (extendable to 21 seconds) |
| Resolution | 480p (Standard) / 720p (Pro/Mega plans) |
| Frame Rate | 24 FPS |
| Audio | None |
| Format | MP4, GIF |

## Video Parameters

| Parameter | Description | Usage |
|-----------|-------------|-------|
| `--video` | Enable video generation | Required - add to prompt with image URL |
| `--raw` | Reduce AI interpretation | For precise motion control |
| Motion Level | Movement intensity | Low (subtle) / High (dynamic) |
| Loop | Seamless loop | Start/end frame match |

### Basic Usage

```
[Image URL] [motion description] --video
```

### With Raw Mode (Precise Control)

```
[Image URL] [motion description] --video --raw
```

## Motion Styles

### Action Style
High-energy movement with dynamic camera work.

```
[Image URL] dynamic movement, action lines, speed effects, high motion --video
```

**Best for**: Shonen action scenes, combat, chase sequences

### Slice-of-Life Style
Gentle, natural movement with subtle animation.

```
[Image URL] gentle breeze, hair flowing softly, subtle movement, peaceful --video --raw
```

**Best for**: Everyday scenes, character moments, atmospheric shots

### Dramatic Style
Cinematic movement with emotional impact.

```
[Image URL] slow camera push, emotional moment, cinematic, medium motion --video
```

**Best for**: Emotional reveals, character close-ups, pivotal moments

### Combat Style
Fast, impactful action with dynamic effects.

```
[Image URL] fast motion, impact frames, explosive movement, high motion --video
```

**Best for**: Fight scenes, special attacks, transformation sequences

## Camera Motion Guide

### Pan (Horizontal/Vertical Movement)

| Direction | Keywords | Example |
|-----------|----------|---------|
| Pan Left | "camera pans left", "tracking left" | `[URL] camera pans left, following character --video` |
| Pan Right | "camera pans right", "tracking right" | `[URL] camera pans right, revealing scene --video` |
| Tilt Up | "camera tilts up", "vertical pan up" | `[URL] camera tilts up, dramatic reveal --video` |
| Tilt Down | "camera tilts down", "looking down" | `[URL] camera tilts down, showing ground --video` |

### Zoom (In/Out Movement)

| Type | Keywords | Example |
|------|----------|---------|
| Zoom In | "camera pushes in", "zoom to face", "dramatic push" | `[URL] slow zoom to face, emotional moment --video` |
| Zoom Out | "camera pulls back", "wide reveal", "zoom out" | `[URL] camera pulls back, revealing environment --video` |

### Orbit (Circular Movement)

| Type | Keywords | Example |
|------|----------|---------|
| Full Orbit | "camera orbits around", "360 rotation" | `[URL] camera orbits around character, showcase --video` |
| Partial Orbit | "camera arcs around", "semi-circle" | `[URL] camera arcs around, dynamic angle --video` |

### Static (Character Animation Only)

| Type | Keywords | Example |
|------|----------|---------|
| Breathing | "subtle breathing", "chest movement" | `[URL] subtle breathing motion, peaceful --video --raw` |
| Hair/Cloth | "hair swaying", "cloth flowing" | `[URL] hair gently swaying, soft breeze --video` |
| Cinemagraph | "minimal movement", "loop" | `[URL] eyes blinking, subtle movement, seamless loop --video` |

## Genre-Specific Motion Presets

### Shonen

High energy, dynamic camera, action-focused.

```
[Image URL] dynamic tracking shot, action lines, high energy, impact frames, fast motion --video
```

**Keywords**: action lines, impact frames, dynamic movement, speed effects, high motion

### Seinen

Atmospheric, slow pans, detailed and moody.

```
[Image URL] slow atmospheric pan, cinematic, detailed, moody lighting, medium motion --video
```

**Keywords**: atmospheric, cinematic, slow pan, moody, subtle motion

### Shoujo

Soft, sparkly, romantic movement.

```
[Image URL] sparkle effects, soft focus, flowing hair, gentle movement, dreamy --video
```

**Keywords**: sparkle effects, soft focus, flowing, dreamy, gentle motion

### Slice of Life

Natural, peaceful, everyday movement.

```
[Image URL] gentle breeze, natural movement, peaceful atmosphere, subtle --video --raw
```

**Keywords**: gentle breeze, natural, peaceful, subtle, low motion

### Mecha

Mechanical precision, transformation sequences.

```
[Image URL] mechanical movement, precise motion, transformation, metallic, dynamic --video
```

**Keywords**: mechanical, precise, transformation, metallic, hydraulic

### Horror

Unsettling, creeping movement, building tension.

```
[Image URL] creeping motion, shadows moving, subtle unease, slow zoom, tension --video
```

**Keywords**: creeping, shadows, unease, slow, tension, low motion

## Loop Animation

Create seamless looping animations where the end frame matches the start.

### Basic Loop

```
[Image URL] seamless loop, gentle breathing, subtle movement --video loop
```

### Cinemagraph-Style Loop

```
[Image URL] cinemagraph, single element moving, hair swaying, rest still, seamless --video loop --raw
```

### Perfect Loop Tips

- Keep motion simple and cyclical
- Use `--raw` for more control
- Subtle movements loop better than dramatic ones
- Hair, cloth, and breathing work well

## Integration with Anime-MJ Features

### With Artist Styles

Generate image with artist style, then animate:

```
# Step 1: Generate image
A warrior in dark armor, Kentaro Miura style, Berserk, dark fantasy --niji 6 --style expressive --ar 16:9

# Step 2: Animate (on web app)
[Generated Image URL] cape flowing dramatically, wind effect, atmospheric, medium motion --video
```

### With SREF Codes

SREF codes apply to image generation, not video. Generate styled image first:

```
# Step 1: Generate with SREF
A magical forest spirit, ethereal glow --niji 6 --style scenic --ar 16:9 --sref 3408846050

# Step 2: Animate
[Generated Image URL] magical particles floating, gentle movement, ethereal --video
```

### With Character Reference

Character reference works with video for consistency:

```
[Image URL] character walking forward, natural movement --video --cref [reference URL] --cw 100
```

## Motion Level Guide

| Level | Effect | Best For |
|-------|--------|----------|
| Low Motion | Subtle, gentle movement | Cinemagraphs, peaceful scenes, character portraits |
| Medium Motion | Balanced, natural movement | Most scenes, general animation |
| High Motion | Dynamic, energetic movement | Action scenes, combat, dramatic moments |

### Specifying Motion Level

Include motion intensity in your prompt:

```
# Low motion
[URL] subtle breathing, minimal movement, peaceful --video --raw

# High motion
[URL] explosive action, dynamic movement, high energy --video
```

## Example Prompts

### Action Scene

```
[Image URL] dynamic camera tracking, speed lines effect, impact frame, explosive movement, high motion --video
```

### Peaceful Moment

```
[Image URL] gentle breeze through hair, soft fabric movement, peaceful atmosphere, low motion --video --raw
```

### Dramatic Reveal

```
[Image URL] slow cinematic zoom to face, emotional intensity, dramatic lighting, medium motion --video
```

### Character Showcase

```
[Image URL] camera slowly orbits around character, full body rotation, showcase pose --video
```

### Seamless Loop

```
[Image URL] seamless loop, hair gently swaying, soft breathing motion, subtle --video loop --raw
```

### Combat Impact

```
[Image URL] fast motion blur, impact frame, explosive energy, dynamic camera shake --video
```

## Tips for Better Animation

1. **Composition matters**: Images with clear subjects animate better
2. **Use --raw for control**: Reduces AI interpretation, follows prompt more closely
3. **Match motion to mood**: Action scenes need high motion, peaceful scenes need low
4. **Simple loops work best**: Complex motion is harder to loop seamlessly
5. **Front-facing works well**: Characters facing camera animate more naturally
6. **Consider aspect ratio**: Wider ratios (16:9, 21:9) suit cinematic motion
7. **Clean backgrounds help**: Busy backgrounds can create distracting movement

## Platform Note

Video generation is **only available on the Midjourney web app** at midjourney.com. You cannot generate videos through the Discord bot.

**Workflow**:
1. Generate anime image (Discord or web)
2. Copy image URL or use web app's "Animate" button
3. Create animation on web app
4. Download MP4 or GIF
