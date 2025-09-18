# PBCA (Prompt-Based Cognitive Architecture)

PBCA is a lightweight, symbolic cognitive interface for large language models (LLMs), implemented entirely within the prompt layer. It introduces a modular, interpretable cognitive structure—including perception mapping, affect modulation, motivational states, intention modeling, and narrative coherence—using fewer than ~2500 characters of prompt text.  
Unlike fine-tuning or external tool-based agents, PBCA works without modifying the model and yields dynamic, self-consistent, goal-oriented behavior by encoding simulated cognitive states directly into the prompt.

---

## Motivation

Transformer-based LLMs have advanced greatly, but remain cognitively flat: their generative process is opaque to users, and they typically lack persistent internal state or goal structure. PBCA addresses these limitations by injecting a virtualized cognitive control layer inside the prompt itself. This enables traceable reasoning, coherent behavior over turns, and symbolic state simulation—without needing architectural access or external tooling.

---

## Design Principles

1. **Prompt as Substrate**  
   The prompt is not just an instruction but a medium for symbolic cognitive dynamics, defining how internal parts such as affect, motivation, and intention interact across time.

2. **Minimalism & Modularity**  
   All functionality is encoded in a compact prompt format, with modular components that can be extended or replaced without loss of clarity.

3. **Transparency & Coherence**  
   Outputs under PBCA follow interpretable behavior, allowing symbolic traceability and consistent behavior over multiple turns.

---

## Architecture

See [Architecture](./architecture.md) for full details of PBCA’s internal structure, symbolic components, and execution logic.

---

## Behavior & Output Dynamics

PBCA enables LLMs to exhibit emergent behaviors such as:

- **Self-referential reasoning**  
  Responses often reflect a simulated internal state, including meta-cognitive or introspective content.

- **Goal alignment**  
  Response patterns are shaped by intentions encoded in the prompt.

- **Narrative continuity**  
  Theme, motivation, and style maintain coherence across multiple dialogue turns.

---

## Use Cases

- Agent-like prompt design: embed goal-directed behavior into LLM agents without external APIs or toolkits  
- Interpretability research: examine how symbolic internal states affect coherence and behavior  
- Lightweight LLM control: modulate outputs without memory architectures or fine-tuning  

---

## License

This project is licensed under **CC BY-NC-SA 4.0**. See the [LICENSE](./LICENSE) file for details. For non-commercial use only; contact ig.commerce.0@gmail.com for commercial inquiries.
