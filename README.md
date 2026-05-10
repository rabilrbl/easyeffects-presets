# EasyEffects Presets

Custom audio enhancement presets for [EasyEffects](https://github.com/wwmm/easyeffects) (PipeWire), tuned for headphone listening.

## AudioFX Balanced

General-purpose enhancement chain with simple compression. Subtle and safe for all content.

**Pipeline: Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Purpose | Key Settings |
|--------|---------|-------------|
| Compressor | Tames loud peaks, lifts quiet detail | Downward, ratio 2:1, threshold -18dB, RMS |
| Bass Enhancer | Adds harmonic bass richness | Amount 12, scope 80Hz, harmonics 8.19 |
| Crystalizer | Sharpens transients and clarity | Progressive intensity (-2 to -14) |
| Stereo Tools | Subtle stereo width expansion | Width 0.8, base 0.15 |
| Limiter | Safety ceiling — no clipping | Herm Thin, threshold -1dB |

## AudioFX Pro

DFX-inspired processing with 6-band multiband compression. Upward compression on sub-bass and highs restores what lossy encoding cuts; downward compression on mids keeps things controlled.

**Pipeline: Multiband Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Purpose | DFX Equivalent | Key Settings |
|--------|---------|---------------|-------------|
| Multiband Compressor (6-band) | Frequency-aware dynamics: upward on sub-bass & highs, downward on mids | Dynamic Boost + Fidelity | Bark-scale bands, RMS per-band |
| Bass Enhancer | Sub-harmonic bass generation | Hyperbass | Amount 14, scope 100Hz, harmonics 8.5 |
| Crystalizer | High-frequency detail restoration | Fidelity | Progressive intensity (-2 to -14) |
| Stereo Tools | Spatial width | 3D Surround + Ambience | Width 0.8, base 0.15 |
| Limiter | Brick-wall protection | — | Herm Thin, threshold -1dB |

## AudioFX Music

Tuned for music listening. Punchier MBC on the mid-bass band for kick drum impact, wider stereo for immersion, and stronger crystalizer with a V-shape curve (peaks in upper mids/highs, dips in very high frequencies to avoid fatigue).

**Pipeline: Multiband Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Difference from Pro |
|--------|-------------------|
| MBC | Tighter ratio on mid-bass (2.0), more upward on sub-bass (1.2), faster attacks |
| Bass Enhancer | Amount 16, scope 120Hz, harmonics 9 |
| Crystalizer | V-shape: strong mid-high peak (-15), tapers back above 8kHz to reduce fatigue |
| Stereo Tools | Width 1.0, base 0.2 — wider for music |
| Limiter | Input gain -1dB for extra headroom |

## AudioFX Movie

Optimized for movies/TV. Aggressive compression keeps dialogue audible over explosions, heavy bass enhancement for cinematic impact, maximum stereo width for immersion, and gentle crystalizer that preserves dialogue clarity without fatiguing highs.

**Pipeline: Multiband Compressor → Bass Enhancer → Crystalizer → Stereo Tools → Limiter**

| Plugin | Difference from Pro |
|--------|-------------------|
| MBC | Softer knee on dialogue band (300Hz–2kHz, ratio 2.8), stronger upward on sub-bass for LFE rap, very fast high-band attack for transient clarity |
| Bass Enhancer | Amount 20, scope 150Hz, harmonics 10 — maximum bass for cinematic LFE |
| Crystalizer | Gentle curve (-1 to -7, then tapering back up to -2) — dialogue clarity without harshness |
| Stereo Tools | Width 1.3, base 0.25 — maximum immersive width |
| Limiter | Input gain -2dB, attack 3ms, release 8ms — catches explosive transients |

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
- **Louder overall** → raise Limiter `threshold` toward 0dB

## License

MIT