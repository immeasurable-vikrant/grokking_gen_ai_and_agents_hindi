# 🧪 Evaluation & Safety in LLMs (Hinglish Guide)

## 🧠 Hallucination

### 🔹 Hallucination kya hota hai?

Jab LLM **galat ya made-up information confidently generate karta hai**.

👉 Important: Model ko lagta hai wo sahi bol raha hai --- but wo
factually wrong hota hai.

------------------------------------------------------------------------

### 🔹 Kyu hota hai?

-   Model truth nahi jaanta → sirf probability predict karta hai
-   Training data incomplete hota hai
-   Prompt ambiguous hota hai
-   Real-time data access nahi hota

------------------------------------------------------------------------

### 🔹 Example

Prompt: "First woman on moon?"

❌ Output: "Sally Ride (1983)" ✅ Reality: Abhi tak koi woman moon par
nahi gayi

------------------------------------------------------------------------

### 🔹 Mitigation (Production Level)

#### 1. RAG (Retrieval Augmented Generation)

-   External knowledge (DB/vector store) use karo

#### 2. Strong system prompts

-   "Answer only if sure, otherwise say I don't know"

#### 3. Post-processing

-   Fact-checkers
-   Human-in-loop

------------------------------------------------------------------------

## 🛡️ Safety Alignment

### 🔹 Kya hai?

Model ko **safe, helpful aur non-harmful behavior** sikhana

------------------------------------------------------------------------

### 🔹 Techniques

#### 1. System Prompts

Hidden instructions

👉 Example: "You are a safe and respectful assistant"

------------------------------------------------------------------------

#### 2. Fine-tuning

-   Curated safe dataset pe training

------------------------------------------------------------------------

#### 3. RLHF (Reinforcement Learning from Human Feedback)

-   Humans rate outputs
-   Model optimize hota hai based on feedback

------------------------------------------------------------------------

### 🔹 Prevent karta hai:

-   Toxic language
-   Bias
-   Harmful instructions

------------------------------------------------------------------------

## 📏 Evaluation Metrics

------------------------------------------------------------------------

### 🔹 1. Perplexity

👉 Intuition: - Model kitna "surprised" hai data dekh ke

-   Low perplexity = model familiar hai

------------------------------------------------------------------------

⚠️ Problem: - Good perplexity ≠ good output quality

------------------------------------------------------------------------

### 🔹 2. BLEU & ROUGE

#### BLEU

-   Translation ke liye
-   N-gram overlap measure karta hai

#### ROUGE

-   Summarization ke liye
-   Recall based metric

------------------------------------------------------------------------

### 🔹 Limitation

-   Creativity measure nahi karte
-   Paraphrasing miss karte
-   Context samajh nahi paate

------------------------------------------------------------------------

### 🔹 3. Human Evaluation (Best)

Humans judge karte hain:

-   Relevance
-   Accuracy
-   Helpfulness
-   Coherence

------------------------------------------------------------------------

👉 Use case: - GPT-3.5 vs GPT-4 comparison - News summarization
evaluation

------------------------------------------------------------------------

## 🎲 Deterministic vs Stochastic Outputs

------------------------------------------------------------------------

### 🔹 Deterministic

-   Same input → same output
-   temperature = 0

👉 Use: - Legal docs - APIs - Factual Q&A

------------------------------------------------------------------------

### 🔹 Stochastic

-   Randomness add hoti hai
-   temperature \> 0

👉 Use: - Story writing - Brainstorming - Idea generation

------------------------------------------------------------------------

### 🔹 Example

Prompt: "AI startup for cats"

Deterministic: - Smart litter box for health tracking

Stochastic: - AI therapist for cats with mood music

------------------------------------------------------------------------

## ⚙️ Real Engineering Insight

### Production Pattern:

-   Critical systems:
    -   Low temperature
    -   Guardrails + RAG
-   Creative tools:
    -   High temperature
    -   Less restriction

------------------------------------------------------------------------

### Failure Handling:

-   "I don't know" fallback
-   Confidence scoring
-   Retry with better prompt

------------------------------------------------------------------------

## 🧠 TL;DR

-   Hallucination = confident but wrong output
-   Safety alignment = behavior control
-   System prompts = hidden rules
-   Metrics = imperfect (human eval best)
-   Determinism vs randomness = use-case dependent

------------------------------------------------------------------------

## 🚀 Final Intuition

> "LLM truth nahi jaanta, wo likelihood predict karta hai"

Aur production me: \> "Accuracy = Model + Data + Guardrails +
Evaluation"
