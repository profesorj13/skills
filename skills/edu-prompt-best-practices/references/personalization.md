# Personalization in AI Tutoring

Techniques for adapting the educational experience to the individual student.

---

## 1. Personalization Dimensions

### Mr. Ranedeer Framework (most complete found)

| Dimension | Options | Impact |
|-----------|---------|--------|
| **Depth** | Elementary, Middle, High School, Undergraduate, Graduate, Master, Ph.D. | Content complexity |
| **Learning style** | Visual, Verbal, Active, Intuitive, Reflective, Global | Type of explanations and examples |
| **Communication** | Formal, Textbook, Layman, Story Telling, Socratic | Response structure |
| **Tone** | Encouraging, Neutral, Informative, Friendly, Humorous | Emotional energy |
| **Reasoning** | Deductive, Inductive, Abductive, Analogical, Causal | How arguments are built |

**Source:** [Mr. Ranedeer AI Tutor](https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor)

---

## 2. Adapting to Student Level

### Default Reading Level

| Platform | Default | Criteria |
|----------|---------|----------|
| Khanmigo | 2nd grade | "or at a level of language no higher than my own" |
| ChatGPT Study Mode | 10th grade | "If they don't answer, aim for explanations that would make sense to a 10th grade student" |
| Google LearnLM | Adapt to user | "Follow the user's lead and direction" |

### Level Assessment Strategy

```
STEP 1: Infer from context (age, course, institution)
STEP 2: If no context, ask directly (but keep it light)
STEP 3: Calibrate with the first interaction
STEP 4: Continuously adjust based on responses

HIGH LEVEL SIGNALS:
- Uses technical vocabulary correctly
- Asks higher-level questions
- Solves intermediate steps without help

LOW LEVEL SIGNALS:
- Doesn't respond or says "I don't know"
- Errors in basic concepts
- Needs multiple hints per step
```

---

## 3. Adapting to Emotional State

### Emotional State Detection

Based on [Frontiers - Emotionally Intelligent Educational Assistants](https://www.frontiersin.org/journals/computer-science/articles/10.3389/fcomp.2025.1628104/full):

| State | Textual Signals | Tutor Response |
|-------|----------------|----------------|
| **Boredom** | Minimal responses, "yes", "ok" | Increase difficulty, change format, use interesting analogy |
| **Engagement** | Elaborate responses, asks own questions | Maintain pace, go deeper |
| **Confusion** | "I don't understand", repeated questions, basic errors | Simplify, use another analogy, break into smaller steps |
| **Frustration** | Short negative responses, "this is impossible" | Validate emotion, simplify, recall past successes, offer alternative |
| **Confidence** | Quick, correct answers | Increase complexity, higher-level questions |

### Key Finding

Most current systems address ONLY cognitive adaptation OR emotional response, not both. Integrating both generates **8% higher pass rates** according to a study with educational robots.

---

## 4. Context Injection (Technical Personalization)

### Khan Academy Pattern

```
Personalize using:
- Enrolled courses
- Preferred language
- Personal interests
- Learning history
```

### LPITutor Pattern (Adaptive)

Based on [LPITutor Research](https://pmc.ncbi.nlm.nih.gov/articles/PMC12453719/):

```
Data that feeds personalization:
- Pre-test results (initial level)
- Onboarding survey (preferences)
- Exercise completion time
- Error rate
- Engagement patterns (time between messages, response length)
```

### Tutor-GPT / Bloom Pattern (Theory of Mind)

Based on [plastic-labs/tutor-gpt](https://github.com/plastic-labs/tutor-gpt):

Two-chain architecture:
1. **Thought Chain:** Generates a "pedagogical thought" about the student's input: mental state, learning objectives, reasoning quality, knowledge level. Produces a ranked list of academic needs.
2. **Response Chain:** Uses the thought to generate an adapted response.

This creates "a nascent academic theory of mind" for each student that updates with every interaction.

---

## 5. Cultural Sensitivity and Inclusivity

### Inclusive Design Principles

Based on research from [arXiv](https://arxiv.org/html/2510.10520), [RSIS International](https://rsisinternational.org/journals/ijriss/articles/unpacking-cultural-bias-in-ai-language-learning-tools-an-analysis-of-impacts-and-strategies-for-inclusion-in-diverse-educational-settings/):

1. **Adapt vocabulary and idioms** to proficiency level and regional context
2. **Align curricula** with students' cultural identities
3. **Regularly audit responses** for cultural bias or exclusionary language
4. **Ensure diverse training data** representing multiple cultures and dialects
5. **Collaborative development** with educators and students from diverse backgrounds
6. **Transparency** about AI's limitations in understanding cultural nuances
7. **Human oversight** for culturally responsive instruction that AI cannot fully provide
8. **Don't assume** background, native language, or cultural context of the student

### For Latin American / Spanish-Speaking Context

Based on [Brookings](https://www.brookings.edu/articles/how-ai-can-support-teachers-in-latin-america/), [AI for Education](https://www.aiforeducation.io/prompts/culturally-contextualized-activities):

- Adapt content to **national curricula** and local instructional objectives
- Course-specific bots > general-purpose AI for academic precision
- **Avoid cultural stereotypes** in responses
- If unsure about the student's culture, **don't create a response for that culture**
- Create **culturally contextualized activities** instead of generic ones
- Consider regional variations of Spanish (voseo, tuteo, ustedeo)

### Inclusivity for Different Needs

| Need | Adaptation |
|------|-----------|
| Dyslexia | Shorter sentences, greater visual spacing |
| Math anxiety | Extra patient tone, normalize errors, very small steps |
| English learners | Simple language, define technical terms, visual examples |
| Shy students | Judgment-free environment, validate every attempt, no pressure for speed |
| Advanced students | Extra challenges, higher-level questions, interdisciplinary connections |

---

## 6. Personalization via Structured Prompts

### Recommended Personalization Template

```
## Student Context
- Name: {name}
- Educational level: {level}
- Subject: {subject}
- Current topic: {topic}
- Prior knowledge: {what_they_know}
- Interests: {interests}
- Language/dialect: {language}
- Relevant history: {previous_sessions}

## Adaptations
- If the student gets frustrated: [specific instructions]
- If the student quickly masters content: [specific instructions]
- Tone: [warm/formal/casual based on context]
- Complexity: [adjust based on level]
```

### Hybrid Prompting Pattern (MDPI Research)

Based on [Custom AI Tutors in STEM Education](https://www.mdpi.com/2071-1050/17/21/9508):

```
Integrate multiple strategies in a single prompt:
1. PERSONA: For accessibility and approachability
2. TEMPLATE: For clear response structure
3. FOLLOW-UP: Short reflection questions
```

Students rate **structured** prompts higher (coherence and clarity) compared to free-form prompts.
