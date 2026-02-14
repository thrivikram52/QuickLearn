---
name: teach
description: Generate IIT-student-ready teaching materials for a technical concept
argument-hint: "<concept> e.g., auto-encoders, backpropagation, CNNs"
allowed-tools:
  - Read
  - Write
  - Bash
  - Glob
  - Grep
  - WebSearch
  - WebFetch
---

# QuickLearn — Teaching Materials Generator

Generate comprehensive teaching materials designed for IIT-level students. Produces lecture plans, assignments, and assessment materials.

## Process

1. **Check for existing QuickLearn content**: Look in `./quicklearn/` for the concept. If it exists, build on that foundation. If not, generate fresh.

2. **Research teaching approaches** using WebSearch:
   - How top universities teach this concept
   - Common pedagogical approaches
   - Student misconceptions documented in education research

3. **Create teaching materials**: `./quicklearn/<concept>/teaching/`

   Generate the following files:

   ### `lecture-plan.md`
   - 50-minute lecture breakdown (minute by minute)
   - Whiteboard plan: what to draw and when
   - Key questions to pose at each transition
   - Demonstrations and live coding segments
   - Suggested pre-class reading for students

   ### `assignment.md`
   - Progressive assignment with 3 difficulty tiers:
     - **Tier 1 (Basics)**: Verify understanding of core concepts
     - **Tier 2 (Application)**: Apply the concept to a new problem
     - **Tier 3 (Challenge)**: Extend or modify the concept creatively
   - Each tier has 2-3 problems
   - Include starter code and expected output where relevant

   ### `assessment.md`
   - Short-answer questions (2-3 marks each)
   - Long-answer questions (10-15 marks each)
   - Coding questions with rubric
   - Viva voce questions for oral examination
   - Model answers for all questions

   ### `misconceptions.md`
   - Top 5-10 student misconceptions for this concept
   - Why students develop each misconception
   - How to address and correct each one
   - Diagnostic questions that reveal misconceptions

   ### `slides-outline.md`
   - Slide-by-slide outline (not full slides, but content per slide)
   - Key diagram descriptions for each slide
   - Speaker notes with timing

4. **If code examples exist** in the parent concept, reference them. Otherwise, generate focused teaching code snippets within the markdown files.

## Quality Standards

- Materials should be appropriate for 3rd/4th year IIT CS/EE students
- Assume strong mathematical background (linear algebra, calculus, probability)
- Include both theoretical and practical components
- Progressive difficulty within each document
- All code examples should be in Python
