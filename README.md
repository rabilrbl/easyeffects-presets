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

## AudioFX Pro

Closer to the real DFX Audio Enhancer processing model. Uses multiband compression (upward on sub-bass and highs, downward on mids) to restore dynamics and detail lost to compression — matching DFX's Dynamic Boost and Fidelity effects.

**Pipeline: Multiband Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Purpose | DFX Equivalent | Key Settings |
|--------|---------|---------------|-------------|
| Multiband Compressor (6-band) | Frequency-aware dynamics: upward on sub-bass & highs, downward on mids | Dynamic Boost + Fidelity | Bark-scale bands, RMS per-band |
| Bass Enhancer | Sub-harmonic bass generation | Hyperbass | Amount 14, scope 100Hz, harmonics 8.5 |
| Crystalizer | High-frequency detail restoration | Fidelity | Progressive intensity (-2 to -14) |
| Stereo Tools | Spatial width | 3D Surround + Ambience | Width 0.8, base 0.15 |
| Limiter | Brick-wall protection | — | Herm Thin, threshold -1dB |

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