# m1

A six-key synth that drives a simulated Chladni plate. Press a key and sand on
the LED panel settles onto the still lines of whatever you're playing.

- **Keys 1–6** (or click): sine, triangle, warble, chord, sweep, buzz. Every
  press picks a new random pitch.
- **Knobs:** warble, tone, echo, length. Drag up/down, scroll, or use arrow keys.
- **Scatter** gently resets: the sand drifts to a fresh sprinkle and any ringing
  sound fades out. Knobs and colours stay as they are.

## How the cymatics work

The plate is driven by the real output spectrum (an FFT of what you hear).
Each plate mode, `cos(nπx)cos(mπy) ± cos(mπx)cos(nπy)`, responds like a damped
resonator at a frequency proportional to `n² + m²` (thin-plate bending waves).
Sand only hops where the plate's acceleration beats a gravity threshold, so it
random-walks off the vibrating areas and collects on the nodal lines.

## Run it

It's one HTML file with no build step: open `index.html` in a browser, or
serve the folder (`python3 -m http.server`).
