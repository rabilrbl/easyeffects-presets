# EasyEffects Presets

Custom audio enhancement presets for [EasyEffects](https://github.com/wwmm/easyeffects) (PipeWire), tuned for headphone listening.

## AudioFX Balanced

General-purpose enhancement chain designed as a Linux alternative to Windows AudioFX / DFX Audio Enhancer. Optimized for use with external USB DACs.

**Pipeline: Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Purpose | Key Settings |
|--------|---------|-------------|
| Compressor | Tames loud peaks, lifts quiet detail | Downward, ratio 2:1, threshold -18dB, RMS |
| Bass Enhancer | Adds harmonic bass richness | Amount 12, scope 80Hz, harmonics 8.19 |
| Crystalizer | Sharpens transients and clarity | Progressive intensity (-2 to -14) |
| Stereo Tools | Subtle stereo width expansion | Width 0.8, base 0.15 |
| Limiter | Safety ceiling — no clipping | Herm Thin, threshold -1dB |

## AudioFX MBC

6-band multiband compressor variant with DFX-inspired upward compression on sub-bass and highs. More aggressive processing — useful if you want heavier dynamics control.

**Pipeline: Multiband Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Difference from Balanced |
|--------|--------------------------|
| Multiband Compressor (6-band) | Upward on sub-bass & highs, downward on mids — frequency-aware dynamics |
| Bass Enhancer | Amount 14, scope 100Hz, harmonics 8.5 |
| Crystalizer | Same progressive intensity |
| Stereo Tools | Same stereo width |
| Limiter | Same threshold |

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

## Tweaking

- **More bass punch** → raise Bass Enhancer `amount`
- **Less boomy** → lower `amount` or narrow `scope`
- **More clarity** → lower Crystalizer intensity values (more negative = stronger)
- **Wider soundstage** → raise Stereo Tools `stereo-width`
- **More compression** → lower Compressor `threshold` or raise `ratio`

## License

MIT