# EasyEffects Presets

Custom audio enhancement presets for [EasyEffects](https://github.com/wwmm/easyeffects) (PipeWire), tuned for headphone listening.

## Presets

### AudioFX Balanced

General-purpose enhancement chain. Subtle boosts across the board — good for everyday listening.

| Plugin | Purpose | Key Settings |
|--------|---------|-------------|
| Compressor | Tames loud peaks, lifts quiet detail | Downward, ratio 2:1, threshold -18dB, RMS |
| Bass Enhancer | Adds harmonic bass richness | Amount 12, scope 80Hz, harmonics 8.19 |
| Crystalizer | Sharpens transients and clarity | Progressive intensity (-2 to -14) |
| Stereo Tools | Subtle stereo width expansion | Width 0.8, base 0.15 |
| Limiter | Safety ceiling — no clipping | Herm Thin, threshold -1dB |

### AudioFX Music

Tuned for music listening — punchier bass, wider soundstage, more expressive detail.

| Plugin | Purpose | Key Settings |
|--------|---------|-------------|
| Compressor | Tighter dynamics control | Downward, ratio 3:1, threshold -15dB, fast release |
| Bass Enhancer | Deep bass punch for music | Amount 16, scope 100Hz, harmonics 10 |
| Crystalizer | V-shaped intensity — strong mids/highs, controlled lows | Progressive intensity (-4 to -16) |
| Stereo Tools | Wide soundstage | Width 1.0, base 0.2 |
| Limiter | Headroom protection with input trim | Herm Thin, threshold -1dB, input gain -1dB |

### AudioFX Movie

Optimized for movies and TV — heavy dynamics control for dialogue clarity, deep bass for effects, maximum stereo width for immersion.

| Plugin | Purpose | Key Settings |
|--------|---------|-------------|
| Compressor | Aggressive leveling — keeps dialogue audible over effects | Downward, ratio 4:1, threshold -12dB, soft knee |
| Bass Enhancer | Cinematic low-end rumble | Amount 20, scope 120Hz, harmonics 12 |
| Crystalizer | Dialogue clarity boost with gentle high-end taper | Milder intensity (-2 to -8, tapering back up) |
| Stereo Tools | Maximum immersive width | Width 1.2, base 0.25 |
| Limiter | Extra headroom for dynamic content | Herm Thin, threshold -1dB, input gain -2dB, fast attack |

## Installation

1. Copy the preset `.json` files to your EasyEffects output presets directory:
   ```bash
   # Flatpak
   cp AudioFX*.json ~/.var/app/com.github.wwmm.easyeffects/data/easyeffects/output/

   # Native package
   cp AudioFX*.json ~/.config/easyeffects/output/
   ```

2. Open EasyEffects → Presets → Select a preset

### Autoload

To auto-apply a preset when a specific output device connects:

1. Open EasyEffects → Presets → Autoloading tab
2. Select a preset and your output device
3. Click "Add"

## Tweaking Guide

- **More bass punch** → raise Bass Enhancer `amount`
- **Less boomy** → lower `amount` or narrow `scope`
- **More clarity** → lower Crystalizer intensity values (more negative = stronger)
- **Wider soundstage** → raise Stereo Tools `stereo-width`
- **More compression** → lower Compressor `threshold` or raise `ratio`
- **Louder overall** → raise Limiter `threshold` toward 0dB

## License

MIT