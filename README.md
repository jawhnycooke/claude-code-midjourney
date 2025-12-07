# Anime-MJ: Anime/Manga Prompt Builder for Midjourney

A Claude Code plugin specialized in generating anime and manga art using Midjourney's Niji mode. Features 30+ manga artists, 14 anime studios, and comprehensive genre support for creating authentic anime art.

## Installation

### Option 1: From GitHub (Recommended)

```bash
# Add the marketplace
claude plugin marketplace add https://github.com/jawhnycooke/claude-code-midjourney

# Install the plugin
claude plugin install anime-mj

# Restart Claude Code
```

### Option 2: Manual Installation

1. Clone this repository:
```bash
git clone https://github.com/jawhnycooke/claude-code-midjourney.git
```

2. Copy the plugin to your Claude Code plugins directory:
```bash
cp -r claude-code-midjourney/plugins/anime-mj ~/.claude/plugins/
```

3. Restart Claude Code

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

### Interactive Workflow

1. **Genre Selection** - Shonen, Seinen, Shoujo, Slice of Life, Mecha, Horror
2. **Artist/Studio Style** - Choose from 30+ artists or 14 studios
3. **Subject Description** - Describe your scene
4. **Niji Style Mode** - cute, expressive, scenic, original
5. **Aspect Ratio** - 16:9, 9:16, 1:1, 2:3, etc.
6. **Output** - Ready-to-paste Niji prompt

### Example Output

```
A lone warrior in black armor facing a massive demon in a gothic cathedral, Berserk style, Kentaro Miura, dark fantasy, hyper-detailed linework, dramatic lighting --niji 6 --style expressive --ar 2:3 --s 800
```

## Supported Artists (30+)

### Foundational Masters
| Artist | Style |
|--------|-------|
| Osamu Tezuka | Astro Boy, classic manga, Disney influence |
| Leiji Matsumoto | Space opera, Captain Harlock |
| Go Nagai | Mecha pioneer, Mazinger Z, Devilman |

### Shonen Legends
| Artist | Style |
|--------|-------|
| Akira Toriyama | Dragon Ball, dynamic action, bold colors |
| Eiichiro Oda | One Piece, exaggerated proportions, adventure |
| Masashi Kishimoto | Naruto, ninja themes, dynamic poses |
| Tatsuki Fujimoto | Chainsaw Man, chaotic, horror elements |
| Hajime Isayama | Attack on Titan, dark, dramatic |
| Gege Akutami | Jujutsu Kaisen, modern shonen |
| Kohei Horikoshi | My Hero Academia, superhero |

### Seinen Masters
| Artist | Style |
|--------|-------|
| Kentaro Miura | Berserk, dark fantasy, hyper-detailed |
| Katsuhiro Otomo | Akira, cyberpunk, dystopian |
| Naoki Urasawa | Monster, psychological thriller |
| Junji Ito | Horror, surreal, disturbing |
| Tsutomu Nihei | Blame!, biomechanical |
| Takehiko Inoue | Vagabond, realistic, emotional |

### Shoujo/Josei Masters
| Artist | Style |
|--------|-------|
| Naoko Takeuchi | Sailor Moon, magical girl |
| CLAMP | Cardcaptor Sakura, elegant |
| Rumiko Takahashi | Inuyasha, comedic |
| Ai Yazawa | Nana, fashion-forward |

### Directors/Designers
| Creator | Style |
|---------|-------|
| Hayao Miyazaki | Studio Ghibli, whimsical |
| Makoto Shinkai | Your Name, photorealistic backgrounds |
| Hideaki Anno | Evangelion, mecha, psychological |
| Satoshi Kon | Perfect Blue, surreal |
| Hiroyuki Imaishi | Trigger style, kinetic, explosive |

### Modern Artists
| Artist | Style |
|--------|-------|
| Hirohiko Araki | JoJo, dramatic poses, baroque |
| ONE/Yusuke Murata | One Punch Man, Mob Psycho 100 |
| Sui Ishida | Tokyo Ghoul, watercolor-like |
| Yoshitoshi Abe | Lain, atmospheric, surreal |

## Supported Studios (14)

| Studio | Aesthetic |
|--------|-----------|
| **Studio Ghibli** | Hand-painted, magical realism, nature |
| **Kyoto Animation** | Moe, detailed eyes, fluid animation |
| **MAPPA** | Modern, dynamic action, dark themes |
| **Ufotable** | CGI integration, vibrant, Demon Slayer |
| **WIT Studio** | Cinematic, Attack on Titan |
| **Bones** | Fluid animation, My Hero Academia |
| **Madhouse** | Versatile, Death Note, One Punch Man |
| **Trigger** | Kinetic, exaggerated, Kill la Kill |
| **Shaft** | Avant-garde, Monogatari series |
| **Production I.G** | Ghost in the Shell, detailed sci-fi |
| **Sunrise** | Gundam, mecha specialist |
| **Toei Animation** | Dragon Ball, One Piece |
| **A-1 Pictures** | Sword Art Online, polished |
| **CloverWorks** | Spy x Family, modern |

## Genres

- **Shonen** - Action, adventure, battles, power-ups
- **Seinen** - Mature, dark, psychological
- **Shoujo** - Romance, magical girl, sparkles
- **Slice of Life** - Everyday, school, heartwarming
- **Mecha** - Robots, sci-fi, space
- **Horror** - Dark, disturbing, surreal
- **Isekai** - Fantasy worlds, adventure
- **Cyberpunk** - Dystopian, neon, futuristic

## Niji Parameters

| Parameter | Description |
|-----------|-------------|
| `--niji 6` | Required for anime (always included) |
| `--style cute` | Kawaii, adorable characters |
| `--style expressive` | Mature, dramatic, emotional |
| `--style scenic` | Environmental focus, landscapes |
| `--style original` | Classic anime aesthetic |
| `--ar` | Aspect ratio |
| `--s` | Stylize (0-1000) |
| `--sref` | Style reference code |
| `--cref` | Character reference |

## Repository Structure

```
claude-code-midjourney/
├── plugins/
│   └── anime-mj/
│       ├── .claude-plugin/
│       │   └── plugin.json      # Plugin manifest
│       ├── commands/
│       │   └── anime-mj.md      # Main slash command
│       ├── skills/
│       │   └── SKILL.md         # Autonomous skill
│       └── README.md            # Plugin documentation
├── README.md                    # This file
└── LICENSE                      # MIT license
```

## Example Prompts

### Studio Ghibli
```
A young adventurer discovering a hidden forest spirit, Studio Ghibli style, Hayao Miyazaki, whimsical, enchanting, lush vegetation --niji 6 --style scenic --ar 16:9 --s 500
```

### Dark Fantasy (Berserk)
```
A lone warrior facing a demon in a gothic cathedral, Berserk style, Kentaro Miura, dark fantasy, hyper-detailed linework, atmospheric --niji 6 --style expressive --ar 2:3 --s 800
```

### Cyberpunk (Akira)
```
A courier on a motorcycle through neon-lit Neo Tokyo, Akira style, Katsuhiro Otomo, cyberpunk, rain reflections, intricate machinery --niji 6 --style expressive --ar 21:9 --s 750
```

### Magical Girl
```
A magical girl mid-transformation with sparkles and ribbons, Sailor Moon style, Naoko Takeuchi, magical girl, pastel colors, cosmic background --niji 6 --style cute --ar 9:16 --s 600
```

### JoJo Style
```
A stylish character striking a dramatic pose, JoJo's Bizarre Adventure style, Hirohiko Araki, fashion-forward, muscular, baroque, menacing --niji 6 --style expressive --ar 3:4 --s 700
```

### Horror (Junji Ito)
```
A figure encountering an impossible spiral staircase, Junji Ito style, horror manga, surreal, disturbing, intricate linework, psychological dread --niji 6 --style original --ar 2:3 --s 800
```

## Best Practices

1. **Always use --niji 6** for anime art
2. **Front-load artist/studio names** - they strongly influence output
3. **Match style mode to genre**:
   - Cute: Shoujo, slice of life, kawaii
   - Expressive: Shonen, seinen, action, drama
   - Scenic: Ghibli, backgrounds, landscapes
   - Original: Retro, classic anime
4. **Keep under 60 words** for best results
5. **Use genre keywords** to reinforce the style

## Future Roadmap

- [ ] Video/animation prompt support
- [ ] SREF code library for anime styles
- [ ] Character consistency workflows
- [ ] Manga panel layouts

## License

MIT License - see [LICENSE](LICENSE)

## Contributing

Contributions welcome! Please submit a Pull Request.

## Resources

- [Midjourney Niji Guide](https://www.aiarty.com/midjourney-prompts/midjourney-niji-prompts.htm)
- [Best Manga Artists - CBR](https://www.cbr.com/greatest-mangaka-artists-ranked/)
- [Anime Art Styles Guide](https://doncorgi.com/blog/anime-art-styles/)
