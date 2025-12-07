 Audio-Reactive Manifold

> "The Geometry of Silence"

## 0. Abstract
This project implements a real-time visualization engine that maps audio frequency input (captured via `navigator.mediaDevices`) to a 3D Euclidean space. It utilizes **Three.js** for the render pipeline and the **Web Audio API** for signal processing.

## 1. The Stack & Mathematics
* **Render Engine:** THREE.WebGLRenderer with `ReinhardToneMapping`.
* **Post-Processing:** `EffectComposer` utilizing `UnrealBloomPass` for high-dynamic-range (HDR) glow effects.
* **Signal Analysis:** 512-point Fast Fourier Transform (FFT) to segregate audio into discrete bins (Bass, Mids, Highs).
* **Geometry:** Nested Icosahedrons acting as the core "Atman" and outer "Manifold," reacting to mid and bass frequencies respectively.

## 2. Core Logic
The animation loop calculates delta variances in the byte frequency data array:
$$Scale_{mandala} = 1 + (\frac{Bass_{avg}}{255}) \times 0.8$$
This creates a "breathing" effect synchronized with low-frequency oscillation.

## 3. Usage
1. Clone the repo.
2. Serve via a local server (e.g., `python3 -m http.server`).
3. Click "INVOKE MANDALA" and authorize microphone access.
