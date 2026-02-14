---
name: quiz
description: Generate quiz questions for active recall testing on a technical concept
argument-hint: "<concept> e.g., auto-encoders, transformers, gradient descent"
allowed-tools:
  - Read
  - Write
  - Bash
  - Glob
  - Grep
  - WebSearch
---

# QuickLearn — Quiz Generator

Generate active recall quiz questions to test and reinforce understanding of a technical concept. Quizzes use collapsible answer sections so learners can self-test.

## Process

1. **Check for existing QuickLearn content**: Look in `./quicklearn/` for the concept to generate contextually relevant questions.

2. **Generate quiz file**: `./quicklearn/<concept>/quiz.md`

3. **Structure the quiz across all 7 levels of understanding**:

```markdown
# <Concept> — Quiz

## How to Use
Read each question, think about your answer, then expand the details section to check.

---

## Level 1: Intuition (Warm-up)

### Q1: [Question]
<details>
<summary>Show Answer</summary>

[Detailed answer with explanation]

</details>

### Q2: [Question]
<details>
<summary>Show Answer</summary>

[Detailed answer]

</details>
```

4. **Generate questions per level**:

   | Level | # Questions | Question Style |
   |-------|-------------|----------------|
   | L1 Intuition | 3 | Analogy-based, "explain in plain words" |
   | L2 Overview | 3 | Component identification, architecture |
   | L3 Walkthrough | 3 | "Trace through this input", prediction |
   | L4 Math | 4 | Derivation, "what does this term mean" |
   | L5 Code (High) | 3 | "What does this code do", modification |
   | L6 Code (Scratch) | 3 | Implementation detail, "why this approach" |
   | L7 Teaching | 2 | "How would you explain...", misconceptions |

   **Total: ~21 questions**

5. **Question quality standards**:
   - Questions should test understanding, not memorization
   - Include "what would happen if..." counterfactual questions
   - Include code snippets where relevant (with syntax highlighting)
   - Answers should explain WHY, not just state the answer
   - Mark difficulty: `[Easy]`, `[Medium]`, `[Hard]`

6. **End with a self-assessment rubric**:
   - 18-21 correct: Mastery — ready to teach this concept
   - 14-17 correct: Strong understanding — review weak areas
   - 10-13 correct: Developing — revisit Levels 3-4
   - Below 10: Revisit from Level 1

## If No Parent Concept Exists

Generate the quiz based on general knowledge of the concept. Note that running `/quicklearn <concept>` first would provide better context for the questions.
