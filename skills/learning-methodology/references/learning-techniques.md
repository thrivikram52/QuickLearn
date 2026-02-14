# Learning Techniques — Detailed Guide

## 1. Feynman Method (Simplify to Understand)

Named after Richard Feynman, this technique forces deep understanding by requiring simple explanations.

### How to Apply
1. **State the concept in one sentence** a non-expert would understand
2. **Identify jargon** — every technical term must be explained or replaced
3. **Find the gaps** — if something can't be explained simply, that's where understanding is weakest
4. **Iterate** — simplify, test, refine until a 12-year-old could follow

### Example (Auto-Encoders)
- Bad: "An auto-encoder learns a compressed latent representation via encoder-decoder architecture"
- Good: "Imagine a photocopier that first shrinks an image into a tiny thumbnail, then tries to blow it back up to full size. The better it gets at making the blown-up version look like the original, the better it is at understanding what really matters in the image."

### When to Use
Apply at Level 1 (Intuition) and Level 7 (Teach Mode). Use as the opening hook for every concept.

---

## 2. Spiral Learning (Progressive Depth)

Visit the same concept multiple times, each time adding depth. The 7-level framework IS spiral learning.

### How to Apply
1. **First pass (L1-L2)**: Pure intuition and big picture
2. **Second pass (L3-L4)**: Concrete examples and formal math
3. **Third pass (L5-L6)**: Implementation at two abstraction levels
4. **Fourth pass (L7)**: Synthesis and teaching

### Key Principle
Each level should reference and reinforce earlier levels. Level 4 (Math) should connect back to Level 1 (Intuition). Level 6 (From Scratch) should reference Level 3 (Walkthrough).

---

## 3. Analogy Bridges (Connect the Unknown to the Known)

Every new concept needs a bridge to something already understood.

### How to Apply
1. **Identify the core mechanism** of the concept
2. **Find a real-world parallel** that shares the same mechanism
3. **Map the components** between the analogy and the concept
4. **Acknowledge where the analogy breaks down** (critical for advanced learners)

### Analogy Quality Checklist
- [ ] Maps to a universally known experience
- [ ] Preserves the core mechanism, not just surface similarity
- [ ] Works for at least 3 key components of the concept
- [ ] Breaking points are identified and explained

### Example Analogies
| Concept | Analogy | Mechanism |
|---------|---------|-----------|
| Auto-Encoder | Photocopier with a tiny buffer | Compress → reconstruct |
| Attention Mechanism | Spotlight in a dark room | Selective focus on relevant parts |
| Gradient Descent | Rolling a ball downhill blindfolded | Iterative local optimization |
| Backpropagation | Tracing blame through a chain of events | Credit assignment backwards |
| GAN | Counterfeiter vs detective | Adversarial improvement |
| Dropout | Training with random team members absent | Forced redundancy |

---

## 4. Visual Thinking (Diagram Everything)

Visual representations encode structure that text cannot efficiently convey.

### Diagram Types by Level

| Level | Diagram Type | Purpose |
|-------|-------------|---------|
| L1 Intuition | Simple metaphor illustration | Make the analogy concrete |
| L2 Overview | Architecture/block diagram | Show component relationships |
| L3 Walkthrough | Sequence/flow diagram | Trace data step by step |
| L4 Math | Computation graphs | Show mathematical flow |
| L5 Code (High) | Class/module diagram | Show code architecture |
| L6 Code (Scratch) | Detailed flow with matrices | Show exact computation |

### Mermaid Diagram Guidelines
- Keep diagrams focused on one idea per diagram
- Use color/styling to distinguish input, processing, and output
- Label every arrow with what flows between components
- Include dimensions/shapes for tensor operations where relevant

---

## 5. Active Recall (Test Understanding)

Passive reading creates an illusion of understanding. Active recall breaks this illusion.

### How to Apply
1. **Checkpoint Questions** — 2-3 questions at the end of each level
2. **Explain-Back Prompts** — "In your own words, explain why..."
3. **Predict-Then-Verify** — "Before reading the math, predict what the loss function looks like"
4. **Code Challenges** — "Modify this code to handle [variation]"

### Question Types by Level
| Level | Question Type | Example |
|-------|-------------|---------|
| L1 | Analogy extension | "How does the auto-encoder analogy break for images with very different content?" |
| L2 | Component role | "What happens if we remove the bottleneck?" |
| L3 | Step tracing | "What would the output be if the input were all zeros?" |
| L4 | Mathematical reasoning | "Why does MSE loss make sense here but not for text?" |
| L5 | Architecture variation | "How would you modify this for a variational auto-encoder?" |
| L6 | Implementation detail | "Why do we initialize weights this way?" |
| L7 | Teaching challenge | "How would you explain the bottleneck to a first-year student?" |

---

## 6. Concrete Before Abstract

Always show a specific, worked example before introducing the general principle.

### How to Apply
1. **Start with a specific instance**: "Take this 8x8 grayscale image..."
2. **Walk through the instance**: Show exact numbers, shapes, operations
3. **Generalize**: "For any NxN image..."
4. **Show variations**: How does it change for different inputs?

### Why This Works
- Abstractions without examples are forgettable
- Examples provide hooks for memory
- Specific instances reveal edge cases the abstraction hides
- IIT students especially benefit from seeing concrete numbers before theorems

---

## 7. Chunking and Sequencing

Break complex concepts into digestible chunks, each building on the last.

### How to Apply
1. **Identify prerequisites**: What must be understood before this concept?
2. **Find natural boundaries**: Where does one idea end and another begin?
3. **Order by dependency**: Teach A before B if B depends on A
4. **Limit chunk size**: Each chunk should take 5-10 minutes to understand

### Example Chunking (Auto-Encoders)
1. Dimensionality reduction (why compress data?)
2. Encoder networks (how to compress)
3. Decoder networks (how to reconstruct)
4. Loss functions (how to measure quality)
5. Bottleneck design (how compression affects learning)
6. Variational extension (adding probabilistic thinking)
7. Applications (when to use which variant)

---

## 8. Interleaving

Mix related concepts rather than studying them in isolation.

### How to Apply
- When teaching Auto-Encoders, briefly compare with PCA
- When showing encoder architecture, contrast with discriminator in GANs
- When discussing bottleneck, relate to information bottleneck theory

### Benefits
- Strengthens distinction between similar concepts
- Builds a connected knowledge graph, not isolated facts
- Better long-term retention per cognitive science research
