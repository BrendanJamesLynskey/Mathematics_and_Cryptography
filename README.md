# 🔐 Modern Cryptography Presentation Series

Interactive slide decks covering modern cryptographic systems end-to-end — from the underlying mathematics through NIST standards to SystemVerilog RTL and Python implementations.

## ▶ [Open the Series Landing Page](https://brendanjameslynskey.github.io/Cryptography/)

> **Setup:** Enable GitHub Pages (Settings → Pages → Deploy from `main` branch, `/ (root)` directory), then replace `OWNER` and `REPO` in the link above with your GitHub username and repository name.
>
> Alternatively, open `index.html` locally in any browser — all presentations work offline after first load.

---

## Presentations

| # | Topic | Slides | Status |
|---|-------|--------|--------|
| 01 | Finite Field Arithmetic for Cryptography | 16 | ✅ Complete |
| 02 | Elliptic Curve Cryptography (ECC) | — | Planned |
| 03 | AES — Design & Implementation | 28 | ✅ Complete |
| 04 | Hash Functions & MACs | — | Planned |
| 05 | Public Key Cryptography (RSA, DH) | — | Planned |
| 06 | Digital Signatures (ECDSA, EdDSA) | — | Planned |
| 07 | Post-Quantum Cryptography | — | Planned |
| 08 | Key Exchange Protocols | — | Planned |
| 09 | Side-Channel Attacks & Countermeasures | — | Planned |
| 10 | Crypto Hardware Accelerator Design | — | Planned |



---

## Presentation 01: Finite Field Arithmetic

16 interactive slides covering:

**Theory** — Group → Ring → Field → Finite Field progression. GF(p) prime fields with GF(7) worked examples. GF(2ⁿ) binary extension fields with AES polynomial arithmetic.

**Standards** — Which fields are used in AES, AES-GCM, NIST P-256, Curve25519, Curve448, and SM2 — and the engineering reasons behind each choice.

**Hardware** — SoC/ASIC composite field decomposition, FPGA LUT and Canright S-box designs, Montgomery multiplication with four architecture variants (bit-serial through full-parallel systolic array).

**Code** — Complete SystemVerilog GF(2⁸) multiplier, parameterized modular add/subtract modules, Python GF(2⁸) and GF(p) classes with Fermat inverse.

**Performance** — Throughput comparison from 3.2 Gbps (OpenSSL) to 53 Gbps (45nm ASIC), with area/speed/side-channel trade-off analysis.

---

## Presentation 03: AES — Design & Implementation

28 interactive slides covering:

**Theory** — GF(2⁸) arithmetic recap with xtime(). S-box two-step construction (multiplicative inverse + affine transformation over GF(2)). Complete 16×16 S-box lookup table. ShiftRows with visual before/after state grids. MixColumns MDS matrix with branch number = 5 analysis. AddRoundKey.

**Standards** — Historical context from DES through the AES competition to FIPS 197. Key schedule for all three variants (128/192/256-bit) with RotWord, SubWord, and Rcon. Round structure pseudocode. Decryption via equivalent inverse cipher.

**Implementation** — T-table optimisation fusing SubBytes + ShiftRows + MixColumns into four 256-entry 32-bit tables. AES-NI hardware instruction set (AESENC, AESDEC, AESKEYGENASSIST). Python AES-128 reference implementation. SystemVerilog AES round module with 16 parallel S-box instances.

**Hardware** — Three architecture tiers: basic iterative (3–5 kGE), inner-round pipelined (8–15 kGE), fully unrolled + pipelined (50–170 kGE). Composite-field S-box via GF((2⁴)²) tower decomposition (Canright's 92 GE design). FPGA vs ASIC comparison. Performance from 80 Mbps (8-bit serial) to 53 Gbps (45nm ASIC).

**Security** — Side-channel attack taxonomy: timing (Bernstein 2005), DPA/CPA (Kocher 1999), differential fault analysis. Countermeasures: Boolean masking (d+1 shares), shuffling, bitslicing, dual-rail logic, threshold implementations, TMR. Cryptanalysis status: biclique (2¹²⁶·¹), related-key, Square attacks. Post-quantum: Grover's algorithm and CNSA 2.0 AES-256 mandate.

**Deployment** — Modes of operation (ECB, CBC, CTR, GCM, XTS, CCM, SIV). Real-world usage: TLS 1.3, IPsec, BitLocker, FileVault, WPA3, Intel AES-NI, ARM Crypto Extensions, RISC-V Zkn.

---

## Repository Structure

```
├── index.html                         ← Landing page (links to all presentations)
├── README.md                          ← This file
├── 01-finite-field-arithmetic/
│   └── index.html                     ← Reveal.js interactive slide deck
└── 03-aes-design-implementation/
    └── index.html                     ← Reveal.js interactive slide deck (28 slides)
```

Each presentation is a single self-contained `index.html`. No build step, no npm — just HTML/CSS/JS with CDN-hosted Reveal.js and Google Fonts.

## Slide Controls

| Action | Key |
|--------|-----|
| Next / Previous | `→` `←` or swipe |
| Overview | `Esc` |
| Fullscreen | `F` |
| Export to PDF | append `?print-pdf` to URL |

## Technology

[Reveal.js 4.6](https://revealjs.com) · [highlight.js](https://highlightjs.org) (Monokai) · Playfair Display + DM Sans + JetBrains Mono

## References

FIPS 197 (AES) · NIST SP 800-186 (ECC Curves) · RFC 7748 (Curve25519/448) · FIPS 186-5 (DSS) · Canright, "A Very Compact Rijndael S-box" (2005) · Mathew et al., "53 Gbps AES in 45nm" IEEE JSSC (2011) · Bogdanov et al., "Biclique Cryptanalysis of AES" ASIACRYPT (2011) · Bernstein, "Cache-Timing Attacks on AES" (2005) · Kocher et al., "Differential Power Analysis" CRYPTO (1999) · Daemen & Rijmen, "The Design of Rijndael" (Springer, 2002) · Gaj & Chodowiec, "FPGA and ASIC Implementations of AES" (2009) · Kleppmann, "Implementing Curve25519/X25519" (2020) · Koç et al., "Finite Field Arithmetic for Cryptography," IEEE (2010)

## License

Educational use. Code examples provided as-is. Standards references are to publicly available NIST, IETF, and ISO documents.
