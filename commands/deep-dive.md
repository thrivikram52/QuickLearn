---
name: deep-dive
description: Deep-dive into a specific sub-topic from a previously learned concept
argument-hint: "<sub-topic> e.g., KL divergence in VAEs, attention mechanism in transformers"
allowed-tools:
  - Read
  - Write
  - Bash
  - Glob
  - Grep
  - WebSearch
  - WebFetch
---

# QuickLearn — Deep Dive

Drill deeper into a specific sub-topic that was introduced in a previous `/quicklearn` session. Generate a focused, in-depth exploration.

## Process

1. **Check for existing QuickLearn content**: Look in `./quicklearn/` for related concept folders to build on existing context.

2. **Research the sub-topic** using WebSearch:
   - Find specialized papers and tutorials
   - Look for interactive visualizations or demos
   - Find advanced applications and edge cases

3. **Create a deep-dive file**: `./quicklearn/<parent-concept>/deep-dive-<sub-topic>.md`

   Structure the deep-dive with:

   ### Section 1: Context
   Where this sub-topic fits within the parent concept. Reference the relevant level from the parent.

   ### Section 2: Intuition Deep-Dive
   Extended analogy specifically for this sub-topic. Go deeper than the parent's Level 1.

   ### Section 3: Detailed Walkthrough
   Step-by-step with specific numbers and Mermaid diagrams. More granular than the parent's Level 3.

   ### Section 4: Mathematics In-Depth
   Full derivations, proofs, and mathematical properties. Include edge cases and special conditions.

   ### Section 5: Implementation Details
   If the sub-topic has implementation implications, generate a focused script at `./quicklearn/<parent-concept>/code/deep-dive-<sub-topic>.py`.

   ### Section 6: Common Pitfalls
   What goes wrong in practice. Numerical issues, common bugs, misconceptions.

   ### Section 7: Further Exploration
   Links to papers, advanced resources, related sub-topics to explore next.

4. **End with checkpoint questions** that test deep understanding of this specific sub-topic.

## If No Parent Concept Exists

If no related `/quicklearn` output exists, suggest running `/quicklearn <parent-concept>` first, then offer to proceed with the deep-dive standalone.
