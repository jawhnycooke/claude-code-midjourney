# SREF Code Library for Anime Styles

A curated collection of Midjourney SREF (Style Reference) codes optimized for anime and manga art generation with Niji 6.

## How to Use SREF Codes

### Basic Usage
```
[your prompt] --niji 6 --sref [code]
```

### With Style Weight
```
[your prompt] --niji 6 --sref [code] --sw [0-1000]
```
- `--sw 100` (default) - Standard influence
- `--sw 250-500` - Strong style application
- `--sw 750-1000` - Very strong style dominance

### Blending Multiple Codes
```
[your prompt] --niji 6 --sref [code1] [code2]
```

### Weighted Blending
```
[your prompt] --niji 6 --sref [code1]::2 [code2]::1
```
Higher weight = more influence from that code.

---

## Ghibli/Soft Styles

Warm, nostalgic, nature-inspired aesthetics reminiscent of Studio Ghibli.

| Code | Name | Description | Best For |
|------|------|-------------|----------|
| `3408846050` | Ghibli Vibes | Studio Ghibli atmospheric quality, hand-painted feel | Scenic landscapes, magical realism, nature scenes |
| `918084796` | Anime Serenity | Peaceful, contemplative mood, soft lighting | Quiet moments, character portraits, slice of life |
| `3161604773` | Pastel Garden | Soft colors, garden settings, gentle atmosphere | Flower scenes, spring themes, peaceful environments |
| `3573349435` | Gentle Pastel | Delicate emotional tones, dreamy quality | Emotional scenes, soft character art, romance |
| `13015050` | Spring Melody | Nature-inspired, pastel tones, seasonal beauty | Cherry blossoms, nature backgrounds, seasonal art |
| `200135` | Floral Elegance | Botanical elements, refined aesthetic | Flower arrangements, elegant portraits |
| `2495059220` | Colorful Dreams | Vibrant pastels, dynamic compositions | Magical scenes, fantasy elements |
| `3425736982` | Whimsical Nature | Playful colors, natural themes | Forest spirits, creature designs |

---

## Shonen/Dynamic Styles

Bold, action-oriented aesthetics with high energy and dramatic compositions.

| Code | Name | Description | Best For |
|------|------|-------------|----------|
| `3730983883` | Dynamic Comic | Metallic accents, action-oriented visuals | Battle scenes, hero poses, action shots |
| `910384726` | Vibrant Manga | Classic manga energy, bold colors | Shonen action, tournament scenes |
| `2063895279` | Cheerful Anime | Bright, energetic, expressive | Upbeat characters, comedy scenes |
| `3121740568` | Cyberpunk Anime | Neon colors, futuristic energy | Sci-fi action, cyber themes |
| `3986684218` | Anime Cyber | Digital aesthetic, dynamic poses | Tech warriors, mecha pilots |
| `2694724947` | Bold Expression | Expressive character designs, strong poses | Character showcases, dramatic moments |

---

## Seinen/Dark Styles

Moody, atmospheric, and detailed aesthetics for mature themes.

| Code | Name | Description | Best For |
|------|------|-------------|----------|
| `416523183` | Anime Vampire | Dark, gothic styling, mysterious | Horror, vampires, dark fantasy |
| `2131889852` | Ethereal Fantasy | Magical, otherworldly, atmospheric | Dark magic, mystical scenes |
| `3136260955` | Nostalgia Dark | Retro moody aesthetic | Psychological drama, noir |
| `229704573` | Dark Warrior | Intense, dramatic, combat-ready | Dark heroes, battle-worn characters |
| `1012` | Dark Enigma | Mysterious shadows, deep contrast | Mystery scenes, psychological horror |
| `602` | Gothic Urban | Dark cityscapes, vigilante aesthetic | Urban fantasy, night scenes |
| `755` | Dystopian Tapestry | Bleak futures, detailed decay | Post-apocalyptic, dystopia |
| `1661` | Moody Grunge | Textured darkness, raw emotion | Emotional intensity, angst |

---

## Shoujo/Elegant Styles

Sparkles, soft lighting, and romantic aesthetics for delicate art.

| Code | Name | Description | Best For |
|------|------|-------------|----------|
| `2178024008` | Futuristic Iridescence | Shimmering effects, tech elegance | Magical girl, transformation scenes |
| `3986738193` | Colorful Elegance | Vibrant yet refined, flowing | Fancy costumes, magical effects |
| `851985277` | Ukiyo-e Anime | Traditional Japanese influence | Historical romance, ethereal beauty |
| `5` | Gothic Elegance | Dark romantic, sophisticated | Vampire romance, elegant darkness |
| `9` | Moody Romance | Emotional depth, soft shadows | Romantic drama, emotional scenes |

---

## Retro Styles

80s/90s anime aesthetic with cel-shading and vintage charm.

| Code | Name | Description | Best For |
|------|------|-------------|----------|
| `16809792746` | 80s Retro Anime | Classic 80s OVA look, bold colors | Retro sci-fi, vintage action |
| `3986738193` | 90s Cyberpunk | Late 90s anime aesthetic, detailed | Cyberpunk, tech noir |
| `4292182277` | Dark OVA Style | Dark 80s/90s OVA aesthetic, gritty | Adult anime, experimental |
| `387` | 90s Anime Vibe | Nostalgic 90s feel, cel-shaded | Classic anime recreation |

---

## Modern/Clean Styles

Contemporary anime aesthetics with polished, clean execution.

| Code | Name | Description | Best For |
|------|------|-------------|----------|
| `65` | Neo-Noir Anime | Modern noir with anime flair | Detective stories, urban drama |
| `20` | Bold Anime Noir | Clean lines, strong contrast | Character posters, key visuals |
| `22` | Dark Anime Aesthetic | Elegant darkness, refined | Modern seinen, stylish horror |
| `261` | Modern Fusion | Western-Eastern blend | Crossover styles, unique hybrids |
| `19` | Sci-Fi Horror | Clean sci-fi with horror elements | Space horror, alien encounters |

---

## Parameter Reference

| Parameter | Description | Range |
|-----------|-------------|-------|
| `--sref [code]` | Apply style reference | Numeric code |
| `--sw [value]` | Style weight | 0-1000 (default: 100) |
| `--sv 4` | Use old V7 SREF model | For legacy code compatibility |
| `--sv 6` | Use current SREF model | Default in V7 |

---

## Tips for Best Results

1. **Start with --sw 100** - Default weight, then adjust up/down
2. **Combine SREF with artist styles** - "Kentaro Miura style --sref 416523183" amplifies the aesthetic
3. **Match SREF to --style mode**:
   - Ghibli/Soft codes → `--style scenic`
   - Shonen/Dynamic codes → `--style expressive`
   - Shoujo codes → `--style cute`
   - Dark codes → `--style expressive` or `--style original`
4. **Test codes first** - Generate a simple prompt to see the style before complex scenes
5. **Blend sparingly** - 2 codes max for predictable results

---

## V6/V7 Compatibility

- **V7 users**: Codes work by default with `--sv 6`
- **V6 codes in V7**: Add `--sv 4` if results look different
- **Niji 6**: All codes in this library tested with `--niji 6`

---

## External Libraries

For thousands more SREF codes:

- [sref-midjourney.com/style/niji](https://sref-midjourney.com/style/niji) - 5,500+ codes with visual previews
- [Midlibrary.io](https://midlibrary.io/) - 2,800+ curated codes in 17 categories
- [promptsref.com/niji-6](https://promptsref.com/version/niji-6) - Niji 6 specific collection
- [srefhunt.com/style/anime](https://srefhunt.com/style/anime/) - Anime-focused SREF collection

---

## Example Prompts

### Ghibli Scenic
```
A young girl discovering a hidden forest spirit among ancient trees, Hayao Miyazaki style, magical realism, lush vegetation --niji 6 --style scenic --ar 16:9 --sref 3408846050 --sw 300
```

### Dark Fantasy
```
A lone warrior facing a demon in gothic ruins, Kentaro Miura style, dark fantasy, atmospheric fog --niji 6 --style expressive --ar 2:3 --sref 416523183 --sw 400
```

### 90s Retro Cyberpunk
```
A hacker in neon-lit Tokyo streets, Akira influence, cyberpunk, rain reflections --niji 6 --style original --ar 21:9 --sref 16809792746 --sw 350
```

### Magical Girl
```
A magical girl mid-transformation with sparkles and ribbons, Sailor Moon style, cosmic background --niji 6 --style cute --ar 9:16 --sref 2178024008 --sw 250
```
