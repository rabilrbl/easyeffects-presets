# EasyEffects Presets

Custom audio enhancement presets for [EasyEffects](https://github.com/wwmm/easyeffects) (PipeWire), tuned for headphone listening.

## AudioFX Balanced

A balanced enhancement chain designed as a Linux alternative to Windows AudioFX / DFX Audio Enhancer. Optimized for use with external USB DACs.

**Pipeline: Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Purpose | Key Settings |
|--------|---------|-------------|
| Compressor | Tames loud peaks, lifts quiet detail | Downward, ratio 2:1, threshold -18dB, RMS |
| Bass Enhancer | Adds harmonic bass richness | Amount 12, scope 80Hz, harmonics 8.19 |
| Crystalizer | Sharpens transients and clarity | Progressive intensity (-2 to -14) |
| Stereo Tools | Subtle stereo width expansion | Width 0.8, base 0.15 |
| Limiter | Safety ceiling — no clipping | Herm Thin, threshold -1dB |

### Installation

1. Copy `AudioFX Balanced.json` to your EasyEffects output presets directory:
   ```bash
   # Flatpak
   cp "AudioFX Balanced.json" ~/.var/app/com.github.wwmm.easyeffects/data/easyeffects/output/

   # Native package
   cp "AudioFX Balanced.json" ~/.config/easyeffects/output/
   ```

2. Open EasyEffects → Presets → Select "AudioFX Balanced"

### Autoload

To auto-apply this preset when a specific output device connects:

1. Open EasyEffects → Presets → Autoloading tab
2. Select "AudioFX Balanced" and your output device
3. Click "Add"

### Tweaking

- **More bass punch** → raise Bass Enhancer `amount` (12 → 16-20)
- **Less boomy** → lower `amount` (12 → 6-8) or narrow `scope` below 80Hz
- **More clarity** → lower Crystalizer intensity values (more negative = stronger)
- **Wider soundstage** → raise Stereo Tools `stereo-width` (0.8 → 1.0)
- **More compression** → lower Compressor `threshold` or raise `ratio`
- **Louder overall** → raise Limiter `threshold` toward 0dB

## License

MIT