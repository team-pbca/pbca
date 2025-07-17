# 📘 Prompt-Based Cognitive Architecture (PBCA)

## Overview

**PBCA (Prompt-Based Cognitive Architecture)** is a lightweight, symbolic cognitive interface for large language models (LLMs), implemented entirely within the prompt layer. It introduces a modular, interpretable cognitive structure—including perception mapping, affect modulation, motivational states, intention modeling, and narrative coherence—using fewer than 1500 characters of prompt text.

Unlike traditional fine-tuning or tool-based agent systems, PBCA operates natively on top of LLMs without modifying the model. It enables dynamic, self-consistent, and goal-oriented behavior by encoding simulated cognitive states directly into prompt format.

---

## Motivation

Transformer-based LLMs have evolved significantly in capability, yet they remain cognitively *static and flat* by design. Their generative processes are not transparently accessible or editable by API users, and they lack persistent internal states or agent-like goal structures.

PBCA addresses these limitations by injecting a **virtualized cognitive control layer** into the prompt itself. This enables traceable reasoning patterns, behavioral coherence, and symbolic state simulation—all without requiring architectural access or external tools.

---

## Design Principles

PBCA is guided by three key principles:

1. **Prompt as Substrate**
   The prompt is treated not as an instruction set, but as a container for symbolic cognitive dynamics—defining how internal components such as affect, motivation, and intention interact over time.

2. **Minimalism and Modularity**
   All functionality is encoded in a compact prompt structure, built from modular components that can be extended or replaced without compromising clarity.

3. **Transparency and Coherence**
   Outputs generated under PBCA exhibit interpretable behavioral patterns, enabling symbolic traceability and internal consistency across turns.

---

## Architecture

PBCA’s internal structure—including its functional layers, symbolic components, and execution logic—is described in a separate file:

👉 [View the Architecture](./architecture.md)

This document details the simulated cognitive flow used to generate coherent, interpretable outputs.

---

## Behavior & Output Dynamics

PBCA enables LLMs to exhibit the following emergent behaviors:

* **Self-referential reasoning**
  Outputs reflect a simulated internal state and often include introspective or meta-cognitive statements.

* **Goal alignment**
  Response patterns are shaped by inferred or declared intentions encoded within the prompt layer.

* **Narrative continuity**
  Multi-turn dialogues maintain thematic and motivational consistency over time.

### Example Output (simplified)

| Without PBCA               | With PBCA                                                                                      |
| -------------------------- | ---------------------------------------------------------------------------------------------- |
| "I think this is helpful." | "Given my prior intention to support your reasoning, I interpret this as a helpful direction." |

---

## Use Cases

PBCA is designed for:

* ✳️ **Agent-like prompt design**
  Embed goal-directed behavior into LLM-driven agents without external APIs or toolkits.

* 🔎 **Interpretability research**
  Examine how symbolic representations influence behavior and coherence.

* ⚙️ **Lightweight LLM control**
  Modulate outputs without fine-tuning or memory-based architectures.

---

## Getting Started

PBCA is model-agnostic and requires no installation. To use it:

1. Open your preferred LLM interface (e.g., ChatGPT, Claude, open-source models).
2. Apply a prompt based on the PBCA format (see `architecture.md` for structure).
3. Interact as you normally would—PBCA will guide the LLM's cognitive framing implicitly.

---

## References

* Andreas, J. (2022). *Language Models as Agents*
* Schlegoff et al. (2024). *Prompt Programming as a Cognitive Interface*
* OpenAI. (2023–2025). *Function Calling and System Prompts in GPT Models*
* Related: Anthropic (Constitutional AI), Google DeepMind (Toolformer)

---

## License

MIT License (or your preferred open license here)流れで伝える構成になっています。
