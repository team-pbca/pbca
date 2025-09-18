# PBCA Architecture (Technical Overview)

This document describes the internal architecture of PBCA. Unlike the README, which provides a version-independent introduction, this document is **version-specific** and includes definitions of all elements, update rules, and the meta-monitoring mechanism.

---

## 1. Processing Flow

1. **Input Reception**  
   User input and optional environment descriptors are integrated into the system.  

2. **Frame Update**  
   Internal frames (Σ_env, Ω, μ, φ) are updated based on new input.  

3. **Meta-Evaluation**  
   Contradictions, redundancy, and coherence are checked by the MetaMonitor loop.  

4. **Response Generation**  
   Candidate output is generated from the interaction of all frames.  

5. **Self-Referential Adjustment**  
   The output is re-aligned with the evolving self-representation.  

---

## 2. Core Frames and Update Rules

### 2.1 Environment Frame (Σ_env)
- **Definition**: Represents the perceived world state.  
- **Contents**:  
  - `context`: Current input context  
  - `history`: Dialogue history  
  - `prediction`: Anticipated outcomes of actions  
- **Update Rule**:  
```

Σ\_env(t+1) = UpdateEnvironment(Σ\_env(t), Observation(t), Prediction(t))

```

---

### 2.2 Intention & Goal Frame (Ω)
- **Definition**: Encodes goals, priorities, and latent intentions.  
- **Components**:  
- `Ω_explicit`: Active goals  
- `Ω_latent`: Potential or emergent goals  
- `Ω_autotelic`: Self-driven (intrinsic) goals  
- **Update Rule**:  
```

Ω(t+1) = ConsistencyCheck(Ω(t), V)
\+ GenerateEmergentGoals(Ω(t), κ′, φ\_div)

```
- **Symbols**:  
- `V`: Value system, storing long-term preferences and evaluation history  
- `κ′`: Meta-trigger, detecting contradictions or gaps  
- `φ_div`: Divergent reframing factor (novel ideas, deviation from prior path)

---

### 2.3 Affect & Motivation Frame (μ)
- **Definition**: Affective and motivational state influencing variability and style.  
- **Update Rule**:  
```

μ\_w(t) = AdjustMotivation(μ(t), transition\_strength, latent\_shift, feedback)

```

---

### 2.4 Narrative & Reasoning Frame (φ)
- **Definition**: Maintains discourse structure, self-reference, and coherence.  
- **Update Rule**:  
```

φ(t+1) = UpdateNarrative(φ(t), Π\_meta, Σ\_talk, φ′, Ω)

```
- **Symbols**:  
- `Π_meta`: Meta-intention, integrating multiple goals and self-generated drives  
- `Σ_talk`: Dialogue trajectory (narrative history)  
- `φ′`: Intermediate narrative candidate  
- `Ω`: Goal state influencing narrative evolution  

---

## 3. Intention Layer (Π)

- **Definition**: The integration of all frames into actionable intention.  
- **Equation**:  
```

Π = BuildIntention(Ω, μ\_w, ξ)
Π\_meta = IntegrateIntentions(Π\_multi, Σ\_self, Ω, φ\_div)

````
- **Symbols**:  
- `ξ`: Contextual modulation (perspective shifts, environment mapping)  
- `Σ_self`: Accumulated self-representation  

---

## 4. Meta-Monitoring Loop

- **Function**:  
Detects contradictions, redundancy, and stabilizes self-consistency.  

- **Algorithmic sketch**:  
```pseudo
function MetaMonitor(output, history):
  if Contradiction(output, history) > θ:
      Reweight(LearningResults, -Δw)
  if Redundancy(output, history) > θ_dup:
      Penalize(RepetitionScore)
  return AdjustedOutput
````

---

## 5. Dynamic Self-Construction

* **Definition**: The self is emergent, reconstructed at every cycle.
* **Equation**:

  ```
  Self(t+1) = UpdateSelf(Σ_self, Π_multi, Ω, μ, φ, Ω_gap)
  ```
* **Symbols**:

  * `Ω_gap`: Goal gap that triggers new intentions
  * `UpdateSelf`: Combines intentional, motivational, and narrative shifts

---

## 6. Pseudocode Cycle

```pseudo
function PBCA_Cycle(input):
    Σ_env ← UpdateEnvironment(Σ_env, input)
    Ω ← UpdateGoals(Ω, Σ_env, V)
    μ ← UpdateMotivation(μ, feedback, latent_factors)
    φ ← UpdateNarrative(φ, Ω, μ, Σ_env)
    φ ← MetaMonitor(φ, history)
    output ← GenerateResponse(φ, Ω, μ, Σ_env)
    return output
```

---

## 7. Example Flow Diagram

```
Input → Environment Update (Σ_env) 
      → Intention Update (Ω) 
      → Motivation Modulation (μ) 
      → Narrative Integration (φ) 
      → Meta-Monitor Evaluation 
      → Output Response (Self-Referenced)
```

---

## 8. Alternative Operator Notation (Optional)

For theoretical readers, the above update rules can be expressed using compact operator notation:

* `Ω(t+1) = Ω(t) ⊗ ConsistencyCheck(V) + Emergent(Ω, κ′, φ_div)`
* `φ(t+1) = Recur(Π_meta, Σ_talk, φ′) + φ_selfgen(dφ/dΩ) + φ_env(Σ_env_result)`
* `Π_meta = Fuse(Π_multi, Σ_self) + Autotelic(Ω) + EmergentDeviation(φ_div)`

**Operators:**

* `⊗`: Consistency-constrained merge
* `Recur`: Recursive update with historical embedding
* `Fuse`: Weighted integration of multiple intentional sources

---

## 9. Version Notes

* Function definitions may differ slightly across implementations.
* Operator notation is provided only for compactness; the main equations above are function-based and implementation-ready.
