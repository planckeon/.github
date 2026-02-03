<div align="center">

<img src="https://raw.githubusercontent.com/planckeon/.github/main/logo.png" alt="Planckeon Labs" width="120" height="120">

# Planckeon Labs

**R&D in high-performance computational physics**

[![GitHub](https://img.shields.io/badge/org-planckeon-181717?logo=github)](https://github.com/planckeon)
[![nufast](https://img.shields.io/crates/v/nufast.svg?label=nufast&color=orange)](https://crates.io/crates/nufast)
[![ITN](https://img.shields.io/badge/demo-itn-blue)](https://planckeon.github.io/itn/)

---

*When physics meets systems programming*

</div>

---

## What We Build

High-performance software tools for computational physics. The goal: make software go zoom, then use it to understand the universe.

## Flagship Projects

### [nufast](https://github.com/planckeon/nufast) — Neutrino Oscillations at the Speed of Light

Fast three-flavor neutrino oscillation probabilities in **Rust**, **Zig**, and **WebAssembly**.

Port of the [NuFast algorithm](https://arxiv.org/abs/2405.02400) by P.B. Denton, used in production by T2K and JUNO.

| Feature | What it does |
|---------|--------------|
| **~25 ns/calc** | Zig SIMD beats the original by 4× |
| **PREM Earth model** | Variable density for atmospheric neutrinos |
| **NSI support** | Non-Standard Interactions with complex ε matrix |
| **Sterile neutrinos** | 3+1 model with exact 4-flavor vacuum |
| **WASM (13 KB)** | Runs in the browser at 20M calculations/sec |

```zig
const nufast = @import("nufast");
const dune = nufast.experiments.dune;
const probs = nufast.matterProbability(dune.toMatterParams(), dune.L, dune.E);
// P(νμ → νe) at DUNE baseline in ~25 ns
```

### [Imagining the Neutrino](https://github.com/planckeon/itn) — See Oscillations Happen

**[▶ Launch Demo](https://planckeon.github.io/itn/)**

Interactive 3-flavor neutrino oscillation visualization. Fly through space with a neutrino as its flavor evolves.

- 11 experiment presets (DUNE, T2K, NOvA, KamLAND, IceCube...)
- Real-time probability plots, ternary diagrams, PMNS matrix display
- δCP slider, matter effects, mass ordering toggle
- 7 languages, keyboard shortcuts, URL state sharing
- Powered by nufast WASM (~13 KB, 60 fps)

Built in React + TypeScript + Canvas 2D. 166 tests passing.

---

## More Projects

| Project | Description | Stack |
|---------|-------------|-------|
| [**attn-as-bilinear-form**](https://github.com/planckeon/attn-as-bilinear-form) | Transformer attention via tensor calculus, statistical mechanics, and differential geometry | Zola |
| [**pauliz**](https://github.com/planckeon/pauliz) | Zero-dependency quantum computing simulation | Zig |
| [**autograv**](https://github.com/planckeon/autograv) | Numerical relativity meets automatic differentiation | JAX |
| [**pytrino**](https://github.com/planckeon/pytrino) | Neutrino oscillations at the speed of C (Python/Cython) | Python |

---

## The Story

I'm a physics grad who fell into systems programming. My undergrad thesis was on neutrino oscillation phenomenology—specifically, using the Eigenvalue-Eigenvector Identity (EEI) to derive analytic expressions for oscillation probabilities. That work became `pytrino`, published on PyPI.

Later, I emailed Peter Denton about extending EEI to 4-flavor oscillations (sterile neutrinos). His reply: "analytically much much worse, and also numerically somewhat unstable." But he pointed me to NuFast—his ~100 ns algorithm. I thought: can I beat that?

The Zig port of NuFast runs at **21 ns per calculation** (SIMD f32). That's 4.7× faster than the original.

Not because I'm smarter—because Zig gives you explicit control over everything LLVM cares about. No hidden allocations, no borrow checker overhead, comptime everything.

---

## Why "Planckeon"?

**Planckeons** are theoretical entities at the Planck scale (~10⁻³⁵ m) where quantum mechanics and gravity merge. Recent work models them as wormhole mouths that realize the **ER=EPR conjecture**—the idea that entanglement is geometry.

Just as planckeons bridge quantum and gravitational physics, we build software that bridges theoretical physics and practical computation.

---

## Philosophy

- **Speed matters.** If your simulation takes hours, you'll run it once. If it takes milliseconds, you'll explore the parameter space.
- **Systems programming is underrated in physics.** Most physicists default to Python. That's fine for prototypes. But production tools should be fast.
- **The best abstractions are zero-cost.** Zig and Rust let you write high-level code that compiles to what you'd write by hand.
- **Open source is the way.** All our tools are MIT licensed.

---

<div align="center">

*"The universe is not only queerer than we suppose, but queerer than we can suppose."*
— J.B.S. Haldane

**[planckeon.github.io](https://planckeon.github.io)**

</div>
