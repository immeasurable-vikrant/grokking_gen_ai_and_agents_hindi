# 🧠 Agent Concepts -- Hinglish Guide

## 🔁 Thought → Action → Observation → Iteration Loop

### 🔹 Yeh kya hota hai?

Agent ka **core loop** hota hai:

👉 Soch → Kaam → Result → Repeat

### Steps samjho:

-   🧠 Thought: "Next kya karna hai?"
-   🔧 Action: API ya tool call
-   👀 Observation: Result mila
-   🔁 Iteration: Continue ya stop decide

------------------------------------------------------------------------

### 🔹 Example:

🎯 Goal: "Paris me \$200 ke andar 3 hotels find karo"

1.  Thought: API call karni chahiye\
2.  Action: Hotel API call\
3.  Observation: 7 hotels mile\
4.  Iteration: Filter karke top 3 return

------------------------------------------------------------------------

## 🧠 Memory in Agents

### 🔹 Memory kya hoti hai?

Agent ko cheeze yaad rakhne me help karti hai.

### Types:

1.  Short-term → current task ke liye\
2.  Conversation → chat history\
3.  Long-term → persistent data

------------------------------------------------------------------------

### 🔹 Example:

User: "Maine jo PDF upload ki thi uska summary?"\
👉 Agent ko yaad hona chahiye kaunsi file

------------------------------------------------------------------------

## 📦 Context Window & State

### 🔹 Problem:

LLM sab kuch ek baar me yaad nahi rakh sakta (token limit)

### 🔹 Solution:

-   Summarization
-   Embeddings based retrieval
-   Memory compression

------------------------------------------------------------------------

## 🤝 Multi-Agent Systems

### 🔹 Kya hota hai?

Multiple agents milke kaam karte hain

------------------------------------------------------------------------

### 🔹 Example:

📄 Document Analysis:

1.  Parser Agent → text split\
2.  Summarizer → summary\
3.  QA Agent → answer\
4.  Supervisor → manage

------------------------------------------------------------------------

## 🧭 Planning Strategies

### 🔹 Common Methods:

### 1. ReAct

-   Reason + Act
-   Step by step execution

### 2. Tree of Thoughts

-   Multiple solutions try karta hai
-   Best choose karta hai

### 3. Graph Planning

-   Workflow nodes me divided

------------------------------------------------------------------------

### 🔹 Example:

Support ticket system: - Classify → lookup → escalate

------------------------------------------------------------------------

## ♻️ Iterative Nodes

### 🔹 Kya hota hai?

Loop jo tab tak chalta hai jab tak condition meet na ho

------------------------------------------------------------------------

### 🔹 Example:

Email likhna:

Loop until: - \<100 words\
- company name present\
- quality score high

------------------------------------------------------------------------

## 🛡️ Agent Safety

### 🔹 Problems:

-   Infinite loop\
-   Galat tool usage\
-   Data leak

------------------------------------------------------------------------

### 🔹 Solutions:

-   Loop limit\
-   Guardrails\
-   Output validation\
-   Human approval

------------------------------------------------------------------------

### 🔹 Example:

Web scraping agent: - 3 baar fail → stop

------------------------------------------------------------------------

## 📦 Summary

-   Thought loop = core logic\
-   Memory = context retain\
-   Multi-agent = teamwork\
-   Planning = smart execution\
-   Iteration = retry\
-   Safety = control

------------------------------------------------------------------------

## 🧠 TL;DR

Agent = AI jo sochta hai, plan karta hai, kaam karta hai, aur galti
sudharta hai.

------------------------------------------------------------------------

## ✅ Real Example: Contract Review Agent

🎯 Goal: NDA review automate karna

### Steps:

1.  Clause extract\
2.  Risk detect\
3.  Rewrite suggest\
4.  Loop until score \> 0.85\
5.  Save to system

------------------------------------------------------------------------

### Safety:

-   Email bina approval ke nahi\
-   Max 3 retries

------------------------------------------------------------------------

## 💡 Final Samajh

Agent sirf jawab nahi deta\
👉 Yeh kaam complete karta hai end-to-end 🚀
