# 🔐 Modern Cryptography Presentation Series

Interactive slide decks covering modern cryptographic systems end-to-end — from the underlying mathematics through NIST standards to SystemVerilog RTL and Python implementations.

## ▶ [Open the Series Landing Page](https://brendanjameslynskey.github.io/Cryptography/)

> **Setup:** Enable GitHub Pages (Settings → Pages → Deploy from `main` branch, `/ (root)` directory), then replace `OWNER` and `REPO` in the link above with your GitHub username and repository name.
>
> Alternatively, open `index.html` locally in any browser — all presentations work offline after first load.

---

## Presentations

| # | Topic | Slides | Status |
| --- | --- | --- | --- |
| 01 | Finite Field Arithmetic for Cryptography | 16 | ✅ Complete |
| 02 | Elliptic Curve Cryptography (ECC) | — | Planned |
| 03 | AES — Design & Implementation | — | Planned |
| 04 | Hash Functions & MACs | — | Planned |
| 05 | Public Key Cryptography (RSA, DH) | — | Planned |
| 06 | Digital Signatures (ECDSA, EdDSA, Schnorr) | 25 | ✅ Complete |
| 07 | Post-Quantum Cryptography | 21 | ✅ Complete |
| 08 | Key Exchange Protocols | — | Planned |
| 09 | Side-Channel Attacks & Countermeasures | 22 | ✅ Complete |
| 10 | Crypto Hardware Accelerator Design | 38 | ✅ Complete |



---

## Presentation 01: Finite Field Arithmetic

16 interactive slides covering:

**Theory** — Group → Ring → Field → Finite Field progression. GF(p) prime fields with GF(7) worked examples. GF(2ⁿ) binary extension fields with AES polynomial arithmetic.

**Standards** — Which fields are used in AES, AES-GCM, NIST P-256, Curve25519, Curve448, and SM2 — and the engineering reasons behind each choice.

**Hardware** — SoC/ASIC composite field decomposition, FPGA LUT and Canright S-box designs, Montgomery multiplication with four architecture variants (bit-serial through full-parallel systolic array).

**Code** — Complete SystemVerilog GF(2⁸) multiplier, parameterized modular add/subtract modules, Python GF(2⁸) and GF(p) classes with Fermat inverse.

**Performance** — Throughput comparison from 3.2 Gbps (OpenSSL) to 53 Gbps (45nm ASIC), with area/speed/side-channel trade-off analysis.

---

## Presentation 06: Digital Signatures

25 interactive slides covering:

**Theory** — Hash-then-sign paradigm, authentication/integrity/non-repudiation properties. The ElGamal → DSA → ECDSA → Schnorr → EdDSA family tree. Full mathematical walkthroughs of ECDSA signing/verification with correctness proofs.

**Schemes** — ECDSA deep dive (key generation, signing, verification, deterministic RFC 6979 variant). Schnorr signatures with linearity and batch verification. EdDSA/Ed25519 with deterministic nonces and twisted Edwards curve parameters. Side-by-side comparison table across all three schemes.

**Advanced Protocols** — MuSig2 (n-of-n) and FROST (t-of-n) threshold signatures. Blind and ring signatures overview.

**Standards** — FIPS 186-5 (2023), RFC 8032 (Ed25519/Ed448), RFC 6979 (deterministic ECDSA), BIP 340 (Schnorr for Bitcoin Taproot), FIPS 204 (ML-DSA), FIPS 205 (SLH-DSA). Real-world deployment map: TLS 1.3, blockchain, SSH, mobile/IoT, code signing, PKI.

**Hardware** — ECDSA/EdDSA FPGA accelerator block diagrams and synthesis results (Virtex-5, Alveo U250). ASIC 45nm implementation data (0.257 mm², 532 MHz). Side-channel attack taxonomy (SPA, DPA, EM, fault injection) and countermeasures (Montgomery ladder, scalar blinding, coordinate randomization).

**Post-Quantum** — ML-DSA (CRYSTALS-Dilithium) and SLH-DSA (SPHINCS+) parameter sets, size comparisons, hardware accelerator results. Hybrid transition strategies.

**Code** — Python Ed25519 and ECDSA P-256 implementations. SystemVerilog modular inverse module (Fermat's little theorem via Montgomery exponentiation). ECDSA sign top-level RTL with FSM controller.

**Interactive** — Live ECDSA signing simulator on a toy elliptic curve with sign, verify, and tamper-detection demonstrations.

**Attacks** — Sony PS3 nonce-reuse (2010), Android Bitcoin wallet RNG failure (2013), ROCA TPM vulnerability (2017), Minerva timing side-channel (2019).

---

## Presentation 07: Post-Quantum Cryptography

21 interactive slides covering:

**The Quantum Threat** — Shor's algorithm breaking RSA/ECC/DH in polynomial time. Grover's quadratic speedup against symmetric ciphers. The "Harvest Now, Decrypt Later" attack model. CRQC timeline estimates and CNSA 2.0 mandates.

**Lattice Mathematics** — Interactive 2D lattice visualisation with Closest Vector Problem demo. SVP, CVP, SIVP, GapSVP hard problems. Learning With Errors (LWE): search vs. decision variants, worst-case to average-case reductions (Regev 2005). Ring-LWE and Module-LWE structured variants. Interactive noise parameter demo showing why error makes LWE hard.

**NIST PQC Standards (Aug 2024)** — FIPS 203 (ML-KEM), FIPS 204 (ML-DSA), FIPS 205 (SLH-DSA). Upcoming: FIPS 206 (FN-DSA/FALCON), HQC (code-based KEM backup). NIST IR 8547 deprecation timeline (2035).

**ML-KEM Deep Dive** — Module-LWE construction: K-PKE → Fujisaki-Okamoto transform → IND-CCA2. Full protocol flow diagram (Alice/Bob key exchange). NTT butterfly architecture and ℤ₃₃₂₉ arithmetic. Parameter sets: ML-KEM-512/-768/-1024 with key/ciphertext sizes.

**ML-DSA Deep Dive** — Fiat-Shamir with Aborts paradigm (Lyubashevsky). Module-LWE + Module-SIS security basis. Parameter sets and abort loop mechanics.

**SLH-DSA (SPHINCS+)** — Hypertree architecture: WOTS+ → XMSS → FORS layers. 12 parameter sets across SHA-2/SHAKE, small/fast modes. Conservative hash-only security assumptions.

**Interactive Comparisons** — Switchable bar charts comparing public key, secret key, and ciphertext/signature sizes across all PQC and classical algorithms. Performance benchmarks: ML-KEM vs. X25519 vs. RSA-2048; ML-DSA vs. Ed25519.

**Hardware Implementation** — NTT accelerator architecture for SoC/FPGA/ASIC. Barrett reduction in ℤ₃₃₂₉. Keccak/SHAKE co-processors. Cortex-M4, Artix-7, and 28nm ASIC benchmarks.

**Code** — Python NTT implementation in ℤ₃₃₂₉ with bit-reversed twiddle factors. Pedagogical ML-KEM key generation sketch with CBD sampling.

**Migration** — Hybrid TLS 1.3 key exchange (X25519 + ML-KEM-768). Three-phase migration roadmap. Crypto-agility design principles. Algorithm decision matrix.

---

## Presentation 09: Side-Channel Attacks & Countermeasures

22 interactive slides covering:

**Timing Attacks** — Kocher's 1996 timing attack fundamentals. Vulnerable vs. constant-time string comparison in C. Constant-time conditional select with branchless bitwise arithmetic. Rules for constant-time cryptographic code. The compiler optimisation problem and verification tools (ct-verif, dudect, timecop, Binsec/Rel).

**Power Analysis** — CMOS dynamic power and the Hamming weight/distance models. Simple Power Analysis (SPA) with interactive RSA square-and-multiply trace visualisation. Differential Power Analysis (DPA) and Correlation Power Analysis (CPA) with animated correlation convergence demo. Template attacks and deep-learning SCA extensions (X-DeepSCA, cross-device single-trace attacks).

**Electromagnetic Emanations** — Near-field EM probes, SEMA/DEMA/CEMA techniques. STELLAR countermeasure for lower-metal routing and current-domain signature attenuation (CDSA). Advantages over power analysis: spatial resolution, non-contact measurement, bypass of decoupling capacitors.

**Cache & Microarchitectural Attacks** — AES T-table cache timing (Bernstein 2005). Flush+Reload, Prime+Probe, Evict+Time techniques. Spectre (Variant 1 bounds-check bypass, Variant 2 branch-target injection) and Meltdown (out-of-order execution, delayed exception handling). KPTI, retpoline, IBRS/IBPB, and DAWG mitigations.

**Fault Injection** — Voltage glitching, clock glitching, EM fault injection, laser FI, and RowHammer with cost/practicality comparison. Differential Fault Analysis (DFA) on AES (Piret-Quisquater, 4 faults for full key) and RSA-CRT (Bellcore attack, single faulty signature). Software and hardware countermeasures including redundant computation, infection, and environmental sensors.

**Countermeasures** — Boolean and arithmetic masking with Python masked-SubBytes example. Threshold Implementations (TI) with SystemVerilog AND-gate example and correctness/non-completeness/uniformity properties. DOM, HPC2/PINI, and AGEMA evolution. Hiding techniques: dual-rail logic (WDDL, SABL), shuffling, random delays, physical shielding with active mesh. Constant-time programming in practice (libsodium, BoringSSL, AES-NI). TVLA methodology with interactive t-test visualisation. RSA blinding, ECC scalar/point/projective coordinate blinding. Hardware-level SAH, on-die voltage regulators, active shield mesh, environmental sensors.

**Cost of Protection** — Area (gate equivalents), throughput, randomness per encryption, and traces-to-break comparison table for unprotected vs. TI vs. DOM vs. shuffling+mask vs. SAH AES-128 implementations.

**Case Studies** — EMV smart cards (DPA on DES/3DES), OpenSSL RSA cache timing (Bernstein/Percival 2005), TEMPEST/Van Eck phreaking, Spectre/Meltdown (2018), Plundervolt/VoltPillager (2019–21), ROCA Infineon TPM (2017). Defense-in-depth layered protection strategy across algorithm, software, hardware, and physical layers.

**Interactive Demos** — SPA power trace canvas showing RSA key bit recovery from square/multiply amplitude patterns. Animated CPA correlation convergence showing correct key hypothesis separating from wrong guesses as trace count increases. TVLA t-test visualisation with ±4.5 threshold lines and leakage spike detection.

---

## Presentation 10: Crypto Hardware Accelerator Design

38 interactive slides covering:

**Symmetric Engines** — AES round architecture from iterative (2,645 GE, 94 Mbps) to fully pipelined (742 Gbps multi-core FPGA). S-Box implementation via composite field tower decomposition (Canright), Boyar-Peralta logic minimization, and threshold implementation for DPA resistance. AES-GCM authenticated encryption with GF(2¹²⁸) GHASH unit architectures. SHA-3/Keccak hardware achieving 36.4 Gbps on Virtex-7 with unrolled round optimization.

**Asymmetric / PKC Engines** — RSA Montgomery multiplication hardware in four variants: bit-serial, word-serial (DSP48E1), systolic array, and full-parallel. ECC scalar multiplication hierarchy from modular arithmetic through point operations to full scalar multiply. Edwards25519 FPGA implementation with unified point add/double achieving 1.4 ms per operation.

**Post-Quantum Hardware** — NIST PQC standards (FIPS 203/204/205) and their hardware bottlenecks. NTT butterfly architecture deep dive covering Cooley-Tukey and Gentleman-Sande formulations. NTT hardware architectures: iterative, Multi-Delay Commutator (MDC), Single-path Delay Feedback (SDF), and mixed-radix. Unified Kyber+Dilithium accelerators sharing NTT and Keccak datapaths. PQC SoC integration with RISC-V via bus-attached accelerators and instruction set extensions.

**Side-Channel Defense** — Taxonomy of power analysis (SPA/DPA/CPA/HO-DPA), electromagnetic, timing, and fault-injection attacks. Hardware countermeasures: Boolean masking, threshold implementation (TI) with correctness/non-completeness/uniformity properties, dual-rail logic (WDDL), random shuffling, blinding, EM shielding, and voltage/clock monitors. TVLA validation methodology — Rambus DPA-resistant cores validated to 100M+ traces.

**RTL Examples** — Complete SystemVerilog implementations of AES round logic with 16 parallel composite-field S-Boxes, the Canright tower-field S-Box decomposition (GF(2⁸) → GF(((2²)²)²)), NTT Cooley-Tukey butterfly for ML-KEM, and multiplier-less Montgomery reduction exploiting Kyber's q=3329 structure.

**Implementation Platforms** — ASIC vs. FPGA trade-off analysis across performance, area, power, flexibility, and certification. Crypto instruction set extensions (x86 AES-NI, AArch64, RISC-V Zkn/Zks). Protocol-level offload engines for IPsec, MACsec, and TLS. Complete design flow from algorithm analysis through FIPS 140-3 / Common Criteria certification.

**Performance Benchmarks** — Comparative tables spanning AES implementations (2,645 GE to 742 Gbps), PQC NTT accelerators with area-time product improvements up to 82%, and FALCON ASIC achieving 5.2K signatures/sec at 28 nm.

**Future Directions** — Crypto agility for PQC migration, FHE accelerators (FAB: 456× CPU speedup), ZK-proof hardware, and the convergence of NTT as shared IP across PQC/FHE/ZK applications.

---

## Repository Structure

```
├── index.html                                    ← Landing page (links to all presentations)
├── README.md                                     ← This file
├── 01-finite-field-arithmetic/
│   └── index.html                                ← Reveal.js interactive slide deck
├── 06-digital-signatures/
│   └── index.html                                ← Reveal.js interactive slide deck
├── 07-post-quantum-cryptography/
│   └── index.html                                ← Reveal.js interactive slide deck
├── 09-side-channel-attacks/
│   └── index.html                                ← Reveal.js interactive slide deck
└── 10-crypto-hardware-accelerator-design/
    └── index.html                                ← Reveal.js interactive slide deck
```

Each presentation is a single self-contained `index.html`. No build step, no npm — just HTML/CSS/JS with CDN-hosted Reveal.js and Google Fonts.

## Slide Controls

| Action | Key |
| --- | --- |
| Next / Previous | `→` `←` or swipe |
| Overview | `Esc` |
| Fullscreen | `F` |
| Export to PDF | append `?print-pdf` to URL |

## Technology

[Reveal.js 4.6](https://revealjs.com) · [highlight.js](https://highlightjs.org) (Monokai) · Playfair Display + DM Sans + JetBrains Mono

## References

**Presentation 01:** FIPS 197 (AES) · NIST SP 800-186 (ECC Curves) · RFC 7748 (Curve25519/448) · FIPS 186-5 (DSS) · Canright, "A Very Compact Rijndael S-box" (2005) · Kleppmann, "Implementing Curve25519/X25519" (2020) · Koç et al., "Finite Field Arithmetic for Cryptography," IEEE (2010)

**Presentation 06:** FIPS 186-5 (DSS) · FIPS 204 (ML-DSA) · FIPS 205 (SLH-DSA) · NIST SP 800-186 (ECC Curves) · RFC 6979 (Deterministic ECDSA) · RFC 8032 (EdDSA) · BIP 340 (Schnorr) · Johnson, Menezes, Vanstone, "The ECDSA" (2001) · Bernstein et al., "High-speed high-security signatures" (2011)

**Presentation 07:** FIPS 203 (ML-KEM) · FIPS 204 (ML-DSA) · FIPS 205 (SLH-DSA) · NIST IR 8547 (PQC Transition) · SP 800-208 (LMS/XMSS) · Shor, "Polynomial-Time Algorithms for Prime Factorization" (1994) · Regev, "On Lattices, Learning with Errors" (2005) · Lyubashevsky, Peikert, Regev, "On Ideal Lattices and RLWE" (2010) · Bos et al., "CRYSTALS-Kyber" (2018) · Ducas et al., "CRYSTALS-Dilithium" (2018) · Bernstein et al., "The SPHINCS+ Signature Framework" (2019)

**Presentation 09:** Kocher, "Timing Attacks on Implementations of DH, RSA, DSS" (1996) · Kocher, Jaffe & Jun, "Differential Power Analysis" (CRYPTO 1999) · Chari, Rao & Rohatgi, "Template Attacks" (CHES 2002) · Biham & Shamir, "Differential Fault Analysis" (1997) · Boneh, DeMillo & Lipton, "On the Importance of Checking Cryptographic Protocols for Faults" (1997) · Piret & Quisquater, "A DFA Technique Against SPN Structures" (2003) · Bernstein, "Cache-Timing Attacks on AES" (2005) · Kocher et al., "Spectre Attacks" (2018) · Lipp et al., "Meltdown" (2018) · Nikova, Rechberger & Rijmen, "Threshold Implementations" (2006) · ISW, "Private Circuits: Securing Hardware Against Probing Attacks" (2003) · Das & Sen, "EM and Power SCA: Advanced Attacks and Low-Overhead Countermeasures" (2020) · Schneider, Moradi & Güneysu, "Arithmetic Addition over Boolean Masking" (2015) · Goodwill et al., "TVLA — A Testing Methodology for SCA Resistance" (2011) · NIST SP 800-90B · FIPS 140-3 · Common Criteria ISO/IEC 15408

**Presentation 10:** FIPS 197 (AES) · FIPS 202 (SHA-3) · FIPS 203 (ML-KEM) · FIPS 204 (ML-DSA) · FIPS 205 (SLH-DSA) · FIPS 140-3 (Crypto Module Security) · Canright, "A Very Compact Rijndael S-box" (CHES 2005) · Boyar & Peralta, "New Logic Minimization Techniques" (2010) · Kocher, Jaffe & Jun, "Differential Power Analysis" (CRYPTO 1999) · Montgomery, "Modular Multiplication Without Trial Division" (1985) · Hasan, "53 Gbps Composite-Field AES" (JSSC 2011) · Ouyang et al., "FalconSign" (TCHES 2025)

## License

Educational use. Code examples provided as-is. Standards references are to publicly available NIST, IETF, and ISO documents.
