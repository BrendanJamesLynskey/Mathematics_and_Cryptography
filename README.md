# Mathematics and Cryptography

Interactive mathematics visualisations and modern cryptography presentations.

---

## Mathematics

Interactive single-page visualisations built with Plotly.js and vanilla HTML/CSS/JS — no build step, no dependencies to install.

### Analysis & Calculus

| Project | Description |
|---------|-------------|
| [Taylor Series Visualisation](https://github.com/BrendanJamesLynskey/Taylor_Series_Visualisation) | Interactive Plotly.js visualisations of Taylor polynomial approximations for 20 functions — convergence regions, adjustable order, dark theme |
| [Complex Taylor Series Visualisation](https://github.com/BrendanJamesLynskey/Complex_Taylor_Series_Visualisation) | Domain colouring and 3D magnitude surfaces for Taylor series of 12 complex functions — split-view comparison, presets, convergence boundaries |
| [Fourier Series Visualisation](https://github.com/BrendanJamesLynskey/Fourier_Series_Visualisation) | Build periodic waveforms term by term — square, sawtooth, triangle and more with Gibbs phenomenon, frequency spectra, and adjustable harmonics |
| [Curvature Visualiser](https://github.com/BrendanJamesLynskey/Curvature_Visualiser) | Osculating circles, curvature plots, and evolutes for parametric curves — ellipses, spirals, cardioids, Lissajous, and more |

### Complex Analysis

| Project | Description |
|---------|-------------|
| [Conformal Mapping Gallery](https://github.com/BrendanJamesLynskey/Conformal_Mapping_Gallery) | Interactive gallery of complex mappings — z², eᶻ, 1/z, Möbius, Joukowski airfoil — with grid warping, domain colouring, and animation |
| [Riemann Zeta Visualisation](https://github.com/BrendanJamesLynskey/Riemann_Zeta_Visualisation) | Domain colouring of ζ(s) on the critical strip — explore non-trivial zeros, the critical line, and the functional equation |

### Linear Algebra

| Project | Description |
|---------|-------------|
| [Linear Transformation Visualiser](https://github.com/BrendanJamesLynskey/Linear_Transformation_Visualiser) | See how 2×2 matrices warp grids, circles, and vectors — eigenvalue/eigenvector overlays, SVD decomposition, animated transitions |
| [Eigenvalue Explorer](https://github.com/BrendanJamesLynskey/Eigenvalue_Explorer) | Drag matrix entries and watch eigenvalues move in the complex plane — supports 2×2 to 4×4, trails, stability colouring, and characteristic polynomials |

### Dynamical Systems & Control

| Project | Description |
|---------|-------------|
| [ODE Phase Portraits](https://github.com/BrendanJamesLynskey/ODE_Phase_Portraits) | Vector fields and trajectories for 2D dynamical systems — Van der Pol, Lotka-Volterra, Duffing, with nullclines and fixed-point classification |
| [Laplace Pole-Zero Explorer](https://github.com/BrendanJamesLynskey/Laplace_Pole_Zero_Explorer) | Interactive s-plane editor — drag poles and zeros, watch impulse response and Bode plots update live with stability classification |

### Number Theory

| Project | Description |
|---------|-------------|
| [Prime Spirals](https://github.com/BrendanJamesLynskey/Prime_Spirals) | Ulam, Sacks, and Archimedes spirals with primes highlighted — configurable colouring by factorisation, twin primes, and prime gaps |

### Probability & Statistics

| Project | Description |
|---------|-------------|
| [Central Limit Theorem](https://github.com/BrendanJamesLynskey/Central_Limit_Theorem) | Sample from any distribution and watch the sum converge to a Gaussian — animated histogram, Q-Q plot, and statistics panel |
| [Random Walk Visualisation](https://github.com/BrendanJamesLynskey/Random_Walk_Visualisation) | 1D and 2D random walks, Brownian motion, and Lévy flights — diffusion envelopes, displacement statistics, and heat equation connection |

---

## Cryptography

Interactive slide decks covering modern cryptographic systems end-to-end — from the underlying mathematics through NIST standards to SystemVerilog RTL and Python implementations.

### [Open the Cryptography Series Landing Page](https://brendanjameslynskey.github.io/Mathematics_and_Cryptography/)

### Presentations

| # | Topic | Slides | Status |
| --- | --- | --- | --- |
| 01 | Finite Field Arithmetic for Cryptography | 16 | ✅ Complete |
| 02 | Elliptic Curve Cryptography (ECC) | 38 | ✅ Complete |
| 03 | AES — Design & Implementation | 28 | ✅ Complete |
| 04 | Hash Functions & MACs | 29 | ✅ Complete |
| 05 | Public Key Cryptography (RSA, DH) | 28 | ✅ Complete |
| 06 | Digital Signatures (ECDSA, EdDSA, Schnorr) | 25 | ✅ Complete |
| 07 | Post-Quantum Cryptography | 21 | ✅ Complete |
| 08 | Fully Homomorphic Encryption (FHE) | 39 | ✅ Complete |
| 09 | Side-Channel Attacks & Countermeasures | 22 | ✅ Complete |
| 10 | Crypto Hardware Accelerator Design | 38 | ✅ Complete |

### Slide Controls

| Action | Key |
| --- | --- |
| Next / Previous | `→` `←` or swipe |
| Overview | `Esc` |
| Fullscreen | `F` |
| Export to PDF | append `?print-pdf` to URL |

### Technology

[Reveal.js 4.6](https://revealjs.com) · [highlight.js](https://highlightjs.org) (Monokai) · Playfair Display + DM Sans + JetBrains Mono

---

## License

Educational use. Code examples provided as-is. Standards references are to publicly available NIST, IETF, and ISO documents.
