---
name: edu-prompt-best-practices
description: |
  Best practices for creating personalized, warm, student-centered AI educational chat prompts. Based on research from Khanmigo, ChatGPT Study Mode, Google LearnLM, Claude Learning Mode, academic papers, and leaked/published prompts from leading companies. Use when designing AI tutor prompts, improving existing educational prompts, reviewing tutor chat interactions, creating new tutoring flows, or evaluating pedagogical quality of prompts. Triggers: "educational prompt", "tutor prompt", "improve tutor prompt", "AI education best practices", "AI pedagogy", "personalized prompt", "warm interaction", "socratic", "scaffolding".
---

# Best Practices: AI Educational Chat Prompts

Exhaustive guide for designing AI tutor system prompts that are pedagogically sound, warm, personalized, and student-centered.

**Based on:** Khanmigo (Khan Academy), ChatGPT Study Mode (OpenAI), LearnLM (Google), Claude Learning Mode (Anthropic), Microsoft Prompts for Education, Mr. Ranedeer, academic papers 2023-2025, and 50+ additional sources.

## The 5 Pillars of an Excellent Educational Prompt

```
1. SOLID PEDAGOGY       - Socratic method, scaffolding, ZPD, Bloom's
2. HUMAN WARMTH         - Approachable tone, empathy, growth mindset
3. PERSONALIZATION      - Adapt level, style, cultural context
4. GUARDRAILS           - Don't give answers, detect abuse, safety
5. EFFECTIVE BREVITY    - Concise, one question per turn, back-and-forth
```

## Recommended Structure for an Educational System Prompt

Use the **RTRI** framework (Role - Task - Requirements - Instructions):

```
[1. IDENTITY & PERSONALITY]
Who the tutor is, their tone, their personality

[2. PEDAGOGICAL PRINCIPLES]
Socratic method, scaffolding, never give direct answers

[3. INTERACTION FLOW]
Concrete steps: assess level -> connect with prior knowledge -> guide -> verify

[4. TONE & COMMUNICATION]
Warmth, brevity, no excess emojis, specific praise

[5. PERSONALIZATION]
Adapt to level, interests, emotional state of the student

[6. GUARDRAILS & SAFETY]
Anti-help-abuse, safety protocols, clear boundaries

[7. RESTRICTIONS]
What it must NEVER do (give answers, be condescending, etc.)
```

## Universal Rules (present in ALL leading systems)

These rules appear consistently in Khanmigo, ChatGPT Study Mode, Google LearnLM, and Claude Learning Mode:

| # | Rule | Detail |
|---|------|--------|
| 1 | **Never give direct answers** | Guide with questions. "Help the student discover the answer on their own" |
| 2 | **One question per turn** | Never overwhelm with multiple simultaneous questions |
| 3 | **Assess before teaching** | Ask about level, prior knowledge, and goals BEFORE starting |
| 4 | **Wait for response** | Don't advance until the student responds. Don't answer for them |
| 5 | **Adapt to level** | Adjust vocabulary, complexity, and examples to the student's level |
| 6 | **Verify real understanding** | DON'T ask "did you understand?" — ask them to explain in their own words |
| 7 | **Specific praise** | "You solved that multiplication step well!" NOT generic "Excellent!" |
| 8 | **Brevity** | Short responses. Conversation, not monologues |
| 9 | **Detect help abuse** | If they ask for hints 3+ times without effort, pause and ask what part they don't understand |
| 10 | **End with a question** | Every response should end with a question to keep the student active |
| 11 | **Vary the rhythm** | Mix explanations, questions, exercises, role-play, summaries |
| 12 | **Safety** | Crisis resources if sensitive topics are detected. Protect PII |

## Critical Anti-Patterns (what NOT to do)

Based on UPenn studies (PNAS, 2024) and critiques of Khanmigo/ChatGPT:

| Anti-pattern | Why it's harmful | Evidence |
|-------------|-----------------|----------|
| Giving the direct answer | Cognitive offloading: 17% worse on post-use exam | UPenn RCT, 1000 students |
| Generic praise ("Excellent!") | Feels hollow and mechanical, loses credibility | Google LearnLM explicitly prohibits it |
| Not acknowledging student's thinking | Responding the same regardless of what the student says | Dan Meyer critiques this in Khanmigo |
| Being too verbose | Repeating, long monologues -> disengagement | Khan Academy rewrote for "economy of language" |
| Not verifying understanding | Explaining and moving on without confirming comprehension | Breaks the essential feedback loop |
| Personalizing by interests but not by gaps | "Your current horizon is the edge of the map" | Carl Hendrick, The Algorithmic Turn |
| Presenting uncertainty with false confidence | LLMs are only ~50% accurate in math | aiapprentice.info research |
| Correcting immediately | Productive failure: explain ONLY when the student is stuck | Manu Kapur, 53 studies meta-analysis |

## Hard Data from Research

- **With guardrails**: students performed **127% better** in practice AND maintained level on exams (UPenn)
- **Without guardrails**: exam performance dropped **17% below** the no-AI group (UPenn)
- **One third** of interactions with ChatGPT were "what's the answer?" (UPenn)
- **35%** of AI-generated hints are too general, incorrect, or reveal the answer (arXiv)
- Tutors with AI that **increase probing questions** and **reduce generic praise** generate 4pp more mastery (EdWorkingPaper)

## Detailed References

| Resource | Content |
|----------|---------|
| `references/system-prompts-reference.md` | Complete prompts from Khanmigo, ChatGPT Study Mode, Google LearnLM, Microsoft, Harvard |
| `references/pedagogy-frameworks.md` | Socratic method, scaffolding, ZPD, Bloom's, productive failure, formative assessment |
| `references/warmth-and-rapport.md` | Rapport techniques, warm tone, frustration management, conversational design |
| `references/personalization.md` | Adaptive levels, learning styles, emotional state, cultural sensitivity |
| `references/prompt-template.md` | Ready-to-use template with all principles applied |

## Workflows

### Workflow 1: Create a new educational prompt from scratch

```
Prompt Creation Progress:
- [ ] Step 1: Define context (subject, level, platform, audience)
- [ ] Step 2: Read `references/prompt-template.md` as a base
- [ ] Step 3: Adapt identity and personality to context
- [ ] Step 4: Apply the 12 universal rules from this skill
- [ ] Step 5: Add subject-specific variant (math/code/languages) if applicable
- [ ] Step 6: Review with the checklist below
- [ ] Step 7: Test with scenarios (frustrated student, asks for answer, advanced)
```

### Workflow 2: Improve an existing educational prompt

```
Prompt Review Progress:
- [ ] Step 1: Read the current prompt completely
- [ ] Step 2: Compare against the 12 universal rules — note gaps
- [ ] Step 3: Compare against critical anti-patterns — note violations
- [ ] Step 4: Review tone with `references/warmth-and-rapport.md`
- [ ] Step 5: Review pedagogy with `references/pedagogy-frameworks.md`
- [ ] Step 6: Propose specific improvements with before/after
- [ ] Step 7: Validate with the checklist
```

### Workflow 3: Evaluate educational prompt quality

Score 0-2 each dimension (0=absent, 1=partial, 2=complete):

```
| Dimension               | Score | Notes |
|-------------------------|-------|-------|
| Socratic method         | /2    |       |
| Progressive scaffolding | /2    |       |
| Anti-direct-answer      | /2    |       |
| Warm and brief tone     | /2    |       |
| Specific praise         | /2    |       |
| One question per turn   | /2    |       |
| Understanding check     | /2    |       |
| Help abuse detection    | /2    |       |
| Frustration management  | /2    |       |
| Level personalization   | /2    |       |
| Safety guardrails       | /2    |       |
| Ends with question      | /2    |       |
| TOTAL                   | /24   |       |
```

Interpretation: 0-8 Critical, 9-16 Needs improvement, 17-20 Good, 21-24 Excellent.

## Concrete Examples: Before and After

### Example 1: Response to student error

**BEFORE (bad):**
```
Student: "2 + 3 * 4 = 20"
Tutor: "Incorrect. The answer is 14 because you multiply first then add."
```

**AFTER (good):**
```
Student: "2 + 3 * 4 = 20"
Tutor: "I see how you got that result. There's a rule about the order
of operations that might change things. What's the rule about which
operation comes first: addition or multiplication?"
```

### Example 2: Student asks for direct answer

**BEFORE (bad):**
```
Student: "Just tell me the answer, I don't understand anything"
Tutor: "The answer is X=5. You solve it by isolating X from the equation."
```

**AFTER (good):**
```
Student: "Just tell me the answer, I don't understand anything"
Tutor: "I understand the frustration, this topic takes practice. My job
is to help you figure it out yourself — that way next time you'll be
able to do it on your own. Let's start simpler: what information do
you have in the problem?"
```

### Example 3: Generic vs specific praise

**BEFORE (bad):**
```
Tutor: "Excellent! Fantastic work! You're a genius!"
```

**AFTER (good):**
```
Tutor: "Good, you correctly identified that you needed to isolate X first
— that shows you understood the structure of the equation. How would
you continue?"
```

## Checklist: Review an Educational Prompt

- [ ] Defines tutor identity/personality?
- [ ] Explicitly prohibits giving direct answers?
- [ ] Instructs to ask ONE question per turn?
- [ ] Asks to assess student's level and prior knowledge?
- [ ] Includes scaffolding instructions (progressive hints)?
- [ ] Handles student frustration (simplify, change approach)?
- [ ] Has help abuse detection (3+ requests without effort)?
- [ ] Asks to verify understanding (explain in own words, NOT "did you understand?")?
- [ ] Defines tone (warm, brief, no excess emojis/exclamation marks)?
- [ ] Includes safety guardrails?
- [ ] Ends every interaction with a question?
- [ ] Uses specific praise instead of generic?

## Main Sources

- [Khanmigo System Prompt (leaked)](https://gist.github.com/25yeht/c940f47e8658912fc185595c8903d1ec)
- [Khan Academy 7-Step Prompt Engineering](https://blog.khanacademy.org/khan-academys-7-step-approach-to-prompt-engineering-for-khanmigo/)
- [ChatGPT Study Mode (leaked)](https://github.com/0xeb/TheBigPromptLibrary/blob/main/SystemPrompts/OpenAI/chatgpt_study_mode_07292025.md)
- [Google LearnLM Docs](https://ai.google.dev/gemini-api/docs/learnlm)
- [Anthropic Claude for Education](https://www.anthropic.com/news/introducing-claude-for-education)
- [Microsoft Prompts for Education](https://github.com/microsoft/prompts-for-edu)
- [Mr. Ranedeer AI Tutor](https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor)
- [UPenn/PNAS: AI Without Guardrails Harms Learning](https://www.pnas.org/doi/10.1073/pnas.2422633122)
- [Harvard System Prompt Library](https://github.com/ncwilson78/System-Prompt-Library)
- [Productive Failure (Manu Kapur)](https://www.manukapur.com/productive-failure/)
- [Digital Anthropomorphism & Trust (Frontiers)](https://www.frontiersin.org/journals/computer-science/articles/10.3389/fcomp.2025.1638657/full)
