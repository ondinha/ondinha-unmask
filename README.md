# Ondinha Unmask

**Spectral side-chain ducking: dips a track only at the frequencies where the key is loud, only while it plays. Kick over bass, vocal over guitars.**

A VST3 and Audio Unit plug-in from [Ondinha](https://github.com/ondinha), a DAW 2.0: native AI tools combined with traditional sound engineering tools.

Makes room for one sound inside another. Put it on the bass and feed the kick into its side-chain: the bass dips **only at the frequencies the kick is using, only while the kick hits**, and keeps its full body in between.

It's side-chain compression without the pumping, and a dynamic EQ that sets itself.

**Needs a side-chain:** route the key track (kick, vocal) to the plug-in's side-chain input in your DAW.

## What it's good for

- Kick over bass (default): focus 30-300 Hz, 6 dB.
- Vocal over guitars: focus 300 Hz - 6 kHz, gentle depth, slower release.
- Snare over guitars, synth pads under a lead, music under dialogue.

## Controls

| Control | Range | What it does |
|---|---|---|
| Depth | 0-24 dB | Maximum dip. |
| Threshold | -70 to 0 dB | How loud the key must be to act. |
| Focus low / high | 20 Hz - 20 kHz | Only this range is touched. |
| Attack | 0.5-50 ms |  |
| Release | 10-500 ms |  |
| Output | +-12 dB |  |

## Presets

Built in as host programs (your DAW's preset menu):

- Kick over bass
- Vocal over guitars
- Snare over guitars

## Download and install

Builds will be on the [Releases](../../releases) page.

**macOS:** copy `Ondinha Unmask.vst3` to `~/Library/Audio/Plug-Ins/VST3` and `Ondinha Unmask.component` to `~/Library/Audio/Plug-Ins/Components`, then rescan plug-ins in your DAW.

| Format | Platform |
|---|---|
| VST3 | macOS |
| Audio Unit (AU) | macOS |

Works in any VST3 or AU host: Ableton Live, Logic Pro, Reaper, Bitwig Studio, Cubase, Studio One, FL Studio and others.

## How it works

Track and key are analysed on the same STFT frame (1024 samples at 44.1 / 48 kHz, 75 % overlap). The key is smoothed over ~1/6 octave so the cut follows its tone rather than single bins, and each bin dips with its own attack and release. With the key silent or not connected, the track passes unchanged. Latency: one frame, reported to the host.

## More Ondinha plug-ins

- [Ondinha Bus Comp](https://github.com/ondinha/ondinha-bus-comp): Console-style glue compressor for the mix bus and groups.
- [Ondinha Split EQ](https://github.com/ondinha/ondinha-split-eq): Transient / tonal split EQ: separate gain for the attack and the sustain in every band.
- [Ondinha Limiter](https://github.com/ondinha/ondinha-limiter): True-peak brickwall limiter for mastering, with an optional oversampled clipper.
- [Ondinha Resonance](https://github.com/ondinha/ondinha-resonance): Dynamic resonance tamer for harsh mixes, vocals and guitars: pulls down narrow peaks only while they ring and leaves the broad tone alone.
- [Ondinha Imager](https://github.com/ondinha/ondinha-imager): Multiband stereo imager with mono low end: width for lows, mids and highs on phase-matched Linkwitz-Riley crossovers.
- [Ondinha Delay](https://github.com/ondinha/ondinha-delay): Tempo-synced stereo / ping-pong delay with filtered, saturated feedback and ducking, so the echoes stay out of the way of the vocal.
- [Ondinha Graphic EQ](https://github.com/ondinha/ondinha-graphic-eq): 10-band octave graphic EQ with analog-matched bells (31 Hz - 16 kHz, +-12 dB).
- [Ondinha Tube Air](https://github.com/ondinha/ondinha-tube-air): High-frequency exciter with a tube stage: adds warm even or bright odd harmonics above a frequency, under the untouched signal.

## Feedback

Found a bug or a host where it misbehaves? [Open an issue](../../issues) with your DAW, its version and your OS.
