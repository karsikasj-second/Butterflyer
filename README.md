# Butterflyer
Butterflyer is a real-time generative rhythm instrument written in Python. At its center is a rotating hypersigil inspired by the Shri Yantra, whose continuously changing geometric relationships act as part of the sequencing and modulation system itself. # 🦋 BUTTERFLYER

**A rotating hypersigil that generates evolving breakbeats in real time.**

Butterflyer is an experimental real-time generative rhythm instrument written in Python.

At its center is a continuously rotating hypersigil inspired by the **Shri Yantra**. The geometry is not merely visualization: its moving phase relationships are part of the musical engine itself. Instead of relying on a conventional 16-step sequencer, Butterflyer uses interacting rotations, drift, symmetry, mutation, probability, and spectral change to generate evolving rhythmic structures.

The result lives somewhere between **breakbeat, trip-hop, drum & bass, abstract electronics, generative percussion, and sound art**.

Butterflyer is meant to be played like an instrument, but also observed like a small autonomous rhythmic organism.

---

## ✨ Core idea

The guiding principle is:

> **The Shri Yantra is the sequencer.**

Nine rotating agents move through related but non-identical phase cycles. Their crossings and phase relationships produce percussion events and influence timbre, stereo position, spectral character, and mutation.

Randomness is deliberately constrained. Butterflyer tries not to generate events simply because it can. Apparent accidents arise from:

- rotating phase relationships
- controlled drift
- symmetry and asymmetry
- density
- attraction toward common pulse relationships
- mutation
- previous system state

The aim is a machine that feels as though **something is rotating behind the rhythm**.

---

## 🎛 Current version

The current known-good realtime build is:

```text
butterflyer_v0_01b.py
```

This version uses a more forgiving realtime audio configuration and has been tested successfully with live audio output.

Butterflyer currently synthesizes three broad percussion species internally:

- **BODY** — low, falling, kick-like and membrane-like impacts
- **DUST** — noisy, unstable snare / membrane textures
- **METAL** — short inharmonic and metallic percussion

No drum samples are required for the core instrument.

---

## 🌀 Main controls

| Control | Function |
|---|---|
| **ROTATION** | Controls the temporal circulation / velocity of the hypersigil |
| **DENSITY** | Controls how frequently geometry becomes audible as events |
| **DRIFT** | Allows the internal clocks to diverge and wander |
| **GRAVITY** | Pulls events toward stronger common rhythmic relationships |
| **SYMMETRY** | Couples opposing parts of the geometry |
| **MUTATION** | Controls slow inherited changes in the system |
| **FLUTTER** | Adds microtiming and timbral instability |
| **SPECTRA** | Changes both spectral brightness and the visual colour field |

One of Butterflyer's important design ideas is that **visual colour and sound-state are related** rather than completely separate layers.

---

## 🎹 Performance controls

### Mouse / touchpad

- Drag a knob vertically to change its value
- Scroll over a knob for finer changes

### Keyboard

| Key | Action |
|---|---|
| `Tab` | Select next knob |
| `Shift + Tab` | Select previous knob |
| Arrow keys | Change selected knob |
| `Space` | **REBIRTH** — reseed the current organism |
| `M` | **MUTATE** — apply a restrained mutation |
| `T` | Trigger a test percussion hit |
| `S` | Save approximately the previous 16 seconds to WAV |
| `Esc` | Quit |

---

## 🔧 Installation

Butterflyer currently targets desktop Python on Linux.

Clone or download the repository, then create a virtual environment:

```bash
python3 -m venv .bfly
source .bfly/bin/activate
```

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Then run:

```bash
python butterflyer_v0_01b.py
```

### Python 3.14 note

For Python 3.14, this project uses **pygame-ce** rather than the older `pygame` package.

The source still imports it normally:

```python
import pygame
```

---

## 🔊 Audio troubleshooting

Butterflyer uses `sounddevice` / PortAudio for realtime output.

If PortAudio is missing on Debian or Ubuntu systems, install:

```bash
sudo apt install libportaudio2 portaudio19-dev
```

A simple way to inspect available audio devices is:

```bash
python -c "import sounddevice as sd; print(sd.query_devices())"
```

Butterflyer v0.01b intentionally uses a somewhat larger realtime block size and a forgiving latency setting. The instrument is generative and performance-oriented, but ultra-low latency is currently less important than stable uninterrupted sound.

---

## 💾 Saving audio

Press:

```text
S
```

to save the most recent section of Butterflyer's output as a WAV file.

This is intended as a musical capture function rather than a rendering/export workflow: if an interesting rhythmic organism appears, capture it before it mutates away.

---
