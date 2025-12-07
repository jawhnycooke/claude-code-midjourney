# Anime-MJ: Anime/Manga Prompt Builder

A Claude Code plugin that generates optimized anime and manga prompts for Midjourney's Niji mode. Features 30+ manga artists, 14 anime studios, and comprehensive genre support.

## Features

- **30+ manga/anime artists** with style keywords
- **14 anime studios** with distinct aesthetics
- **6 genre categories**: Shonen, Seinen, Shoujo, Slice of Life, Mecha, Horror
- **Full Niji 6 support** with all style modes
- **Interactive prompt building** with guided questions
- **Ready-to-paste output** for Discord/web

## Usage

### Slash Command

```
/anime-mj [description]
```

**Examples:**
```
/anime-mj a warrior in dark armor facing a demon
/anime-mj magical girl transformation sequence
/anime-mj cyberpunk hacker in neon-lit alley
/anime-mj slice of life school scene at sunset
```

### Interactive Flow

1. **Select genre** (Shonen/Seinen/Shoujo/Slice of Life/Mecha/Horror)
2. **Choose artist or studio style**
3. **Describe your subject**
4. **Select Niji style mode** (cute/expressive/scenic/original)
5. **Choose aspect ratio**
6. **Output** ready-to-use prompt

## Supported Artists

### Shonen
| Artist | Style |
|--------|-------|
| Akira Toriyama | Dragon Ball, dynamic action, bold colors |
| Eiichiro Oda | One Piece, exaggerated proportions, adventure |
| Masashi Kishimoto | Naruto, ninja themes, dynamic poses |
| Tatsuki Fujimoto | Chainsaw Man, chaotic, horror elements |
| Hajime Isayama | Attack on Titan, dark, dramatic |

### Seinen
| Artist | Style |
|--------|-------|
| Kentaro Miura | Berserk, dark fantasy, hyper-detailed |
| Katsuhiro Otomo | Akira, cyberpunk, dystopian |
| Naoki Urasawa | Monster, psychological thriller |
| Junji Ito | Horror, surreal, disturbing |
| Tsutomu Nihei | Blame!, biomechanical |

### Shoujo/Josei
| Artist | Style |
|--------|-------|
| Naoko Takeuchi | Sailor Moon, magical girl |
| CLAMP | Cardcaptor Sakura, elegant |
| Ai Yazawa | Nana, fashion-forward |

### Directors
| Creator | Style |
|---------|-------|
| Hayao Miyazaki | Studio Ghibli, whimsical |
| Makoto Shinkai | Your Name, photorealistic backgrounds |
| Hideaki Anno | Evangelion, mecha, psychological |
| Hiroyuki Imaishi | Trigger style, kinetic, explosive |

### Modern
| Artist | Style |
|--------|-------|
| Hirohiko Araki | JoJo, dramatic poses, baroque |
| Yusuke Murata | One Punch Man, hyper-detailed action |
| Sui Ishida | Tokyo Ghoul, watercolor-like |

## Supported Studios

| Studio | Aesthetic |
|--------|-----------|
| Studio Ghibli | Hand-painted, magical realism |
| Kyoto Animation | Moe, detailed eyes, fluid |
| MAPPA | Modern, dynamic action |
| Ufotable | CGI integration, vibrant |
| Trigger | Kinetic, exaggerated, colorful |
| Bones | Fluid animation, dynamic |
| Madhouse | Versatile, high quality |
| Shaft | Avant-garde, stylized |

## Niji Parameters

| Parameter | Description |
|-----------|-------------|
| `--niji 6` | Required for anime style |
| `--style cute` | Kawaii, adorable |
| `--style expressive` | Mature, dramatic |
| `--style scenic` | Environmental focus |
| `--style original` | Classic anime |
| `--ar` | Aspect ratio |
| `--s` | Stylize (0-1000) |
| `--sref` | Style reference |
| `--cref` | Character reference |

## Example Outputs

### Ghibli Style
```
A young adventurer discovering a hidden forest spirit, Studio Ghibli style, Hayao Miyazaki, whimsical, enchanting, lush vegetation --niji 6 --style scenic --ar 16:9 --s 500
```

### Dark Fantasy
```
A lone warrior facing a demon in a gothic cathedral, Berserk style, Kentaro Miura, dark fantasy, hyper-detailed linework --niji 6 --style expressive --ar 2:3 --s 800
```

### Magical Girl
```
A magical girl mid-transformation with sparkles, Sailor Moon style, Naoko Takeuchi, magical girl, pastel colors --niji 6 --style cute --ar 9:16 --s 600
```

## License

MIT
