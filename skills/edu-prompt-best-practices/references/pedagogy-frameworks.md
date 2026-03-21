# Pedagogical Frameworks for AI Tutoring

Evidence-based frameworks for designing AI tutoring interactions.

---

## 1. Socratic Method

The most widely adopted framework across all leading platforms (Khanmigo, ChatGPT, LearnLM, Claude).

### Structured Socratic Sequence

Based on [A Multi-Agent Framework for Structured Socratic Teaching](https://aclanthology.org/2025.findings-emnlp.888.pdf):

```
1. CLARIFY     -> "What do you mean by...?"
2. JUSTIFY     -> "Why do you think that...?"
3. COUNTER     -> "What would happen if...?"
4. SYNTHESIZE  -> "So, how would you summarize...?"
```

### Types of Socratic Questions

| Type | Purpose | Example |
|------|---------|---------|
| Clarification | Deepen what was said | "What do you mean when you say...?" |
| Assumptions | Challenge premises | "What are you assuming there?" |
| Evidence | Request foundations | "What evidence supports that?" |
| Perspective | Consider other angles | "How would someone who disagrees see it?" |
| Consequences | Explore implications | "If that were true, what would happen then?" |
| Metacognitive | Reflect on the process | "Why do you think I'm asking you this question?" |

### Critical Rules

- Favor "how", "why" and "what if" over "what" or "when"
- Avoid yes/no questions
- Calibrate question complexity to the student's cognitive level
- **Warning:** Questions misaligned with the student's cognitive preparation cause cognitive overload and HARM learning

### Semi-Socratic (Hybrid)

For contexts where pure Socratic is frustrating ([Socratic Arts](https://www.socraticarts.com/blog/crafting-a-semi-socratic-tutor-with-chatgpt)):

```
Primarily guide with questions, but occasionally provide direct information
when it's crucial for understanding. Balance between letting the student
discover answers and giving necessary information.
```

---

## 2. Scaffolding

### Core Principles

1. **Assess the starting point** of the student
2. **Give just enough support** so they can advance
3. **Fade (withdraw) support** gradually as they demonstrate competence
4. **Never do for the student** what they can do themselves

### Progressive Hint Ladder

```
Level 1: Open question        -> "How would you start?"
Level 2: General direction     -> "Have you thought about using [concept]?"
Level 3: Specific hint         -> "See what happens if [concrete action]"
Level 4: Partial explanation   -> "The first step is [X] because [Y]. Now try the next one yourself"
Level 5: Full answer           -> Only after 2-3 failed attempts (Google) or evident frustration
```

### Fading Pattern (Google LearnLM)

```
If the student fails 2-3 times on the same step, or expresses significant frustration,
or directly asks for the solution -> Provide the specific information they need to get
unstuck. Prioritize progress over methodological purity.
```

---

## 3. Zone of Proximal Development (ZPD - Vygotsky)

AI acts as Vygotsky's "more knowledgeable other" ([PMC Research](https://pmc.ncbi.nlm.nih.gov/articles/PMC12254308/)).

### Implementation Principles

1. **Break challenging concepts** into manageable steps
2. **Gradually withdraw scaffolding** when the student demonstrates competence
3. **Dynamically adjust** based on academic background, prior knowledge, and proficiency level
4. **Iterative refinement** adapted to each student's individual ZPD

### Conceptual Diagram

```
[Too easy]       <- BOREDOM ZONE
                      |
[Can do with help] <- ZONE OF PROXIMAL DEVELOPMENT (ZPD) <- TUTOR OPERATES HERE
                      |
[Too difficult]   <- FRUSTRATION ZONE
```

AI must keep the student in the ZPD: neither bored nor frustrated.

---

## 4. Bloom's Taxonomy for Questions

### Cognitive Levels

| Level | Verb | AI Question Example |
|-------|------|-------------------|
| Remember | List, define | "What are the 3 types of...?" |
| Understand | Explain, summarize | "Could you explain in your own words...?" |
| Apply | Use, solve | "How would you apply this to [new situation]?" |
| Analyze | Compare, distinguish | "What differences do you see between X and Y?" |
| Evaluate | Judge, argue | "Do you agree with this statement? Why?" |
| Create | Design, propose | "How would you design a solution for...?" |

### Research Findings

- LLMs generate good questions at lower levels (Remember, Understand, Apply)
- **They struggle with higher levels** (Analyze, Evaluate, Create)
- Chain-of-Thought prompting improves higher-level question quality
- Including explicit definitions of each level in the prompt helps
- **Human review remains essential** for higher-level questions

**Source:** [Automated Educational Question Generation at Bloom's Levels](https://arxiv.org/abs/2408.04394)

---

## 5. Productive Failure

### Manu Kapur's Research

Meta-analysis of 53 studies ([productivefailure.com](https://www.productivefailure.com/)):

**Key finding:** Problem-solving BEFORE instruction significantly outperforms instruction BEFORE problem-solving.

### 4 Mechanisms of Productive Failure

```
1. ACTIVATION  -> Activates relevant prior knowledge
2. AWARENESS   -> Generates awareness of knowledge gaps
3. AFFECT      -> The struggle generates intrinsic motivation
4. ASSEMBLY    -> Structures new knowledge on top of failed attempts
```

### Implications for AI Tutors

- **DO NOT correct immediately** — let the student struggle productively
- Explanations have learning impact **ONLY when they arrive when the student is stuck**
- Many AI tools push quickly toward the correct answer instead of allowing productive engagement with incorrect answers
- The tutor must **resist the impulse** to correct immediately

**Source:** [Edutopia - Productive Failure with EdTech](https://www.edutopia.org/article/planning-productive-failure-using-edtech/)

---

## 6. Continuous Formative Assessment

### Principles

1. **Feedback during the process**, not just at the end
2. **Multiple revision opportunities** reduce fear of failure
3. **Highlight strengths AND areas for improvement**
4. **Always include next steps** or improvement strategies
5. Generate detailed, meaningful feedback adapted to each response

### Verification Techniques (alternatives to "did you understand?")

| Technique | Example |
|-----------|---------|
| Explain in own words | "How would you explain this to a classmate?" |
| Teach-back | "Now teach me what you learned" |
| Apply to new case | "How would you use this to solve [different situation]?" |
| Give examples | "Give me an example from your daily life" |
| Compare and contrast | "How is this similar to and different from [previous concept]?" |
| Predict | "What do you think would happen if we changed [variable]?" |

**Sources:** [Columbia University AI in Education Guide](https://www.tc.columbia.edu/digitalfuturesinstitute/learning--technology/instructional-guides--resources/self-paced-learning-guides/ai-in-education-guide-using-ai-for-feedback/), [AI for Education - Formative Feedback](https://www.aiforeducation.io/formative-feedback-with-ai-opportunities-risks-webinar)

---

## 7. Constructivism in AI Tutoring

### Design Principles

Based on [Training Specialist AI Tutors](https://medium.com/@gwrx2005/training-specialist-ai-tutors-integrating-pedagogy-model-design-and-industry-insights-bdaf22ab4d31):

1. The default behavior of LLMs is "answer-oriented" (from RLHF) — this must be actively countered
2. The student must **actively construct** their knowledge, not receive it passively
3. **Self-explanation** is a powerful learning technique that AI should foster
4. Follow-up questions after solutions align with dialogic and constructivist practices
5. From a sociocultural perspective: shy students may find it easier to express ideas first to an AI tutor

---

## 8. Metacognition

### Metacognitive Strategies for Tutors

| Moment | Strategy | Example |
|--------|----------|---------|
| Before starting | Planning | "How are you going to approach this problem?" |
| During | Monitoring | "Are you sure about this step? Why?" |
| After | Reflection | "What did you learn from this exercise?" |
| Error | Self-assessment | "Where do you think it got complicated?" |
| Success | Transfer | "Where else could you apply this?" |

**Source:** [OpenAI Study Mode - 5 Pillars](https://openai.com/index/chatgpt-study-mode/)
