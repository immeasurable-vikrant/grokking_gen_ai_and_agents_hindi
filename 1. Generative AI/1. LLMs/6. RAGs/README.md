# 🔍 RAG (Retrieval-Augmented Generation) -- Hinglish Guide

## 🧠 RAG kya hai?

RAG ka matlab hai **Retrieval + Generation**.

Simple words me: LLM ko sab kuch yaad nahi hota, toh hum external data
(documents, PDFs, database) se **relevant info nikaalte hain
(retrieve)** aur fir LLM ko dete hain **better answer generate karne ke
liye**.

------------------------------------------------------------------------

## ❓ Problem kya hai?

LLMs ki limitation: - Limited context (8k--200k tokens) - Purana data
bhool jaate hain - Sab data ek baar me dena expensive hai

### Example:

User poochta hai: "What happened in June 2023 earnings?"

❌ Galat approach: Saari company history feed karna

✅ Sahi approach (RAG): Sirf June 2023 ka relevant part retrieve karo →
LLM ko do → answer lo

------------------------------------------------------------------------

## 🧬 Embeddings kya hote hain?

Embeddings = Text ko numbers (vectors) me convert karna

Example: "Apple profits increased" "Company revenue grew"

👉 Dono ka meaning similar hai → embeddings bhi similar honge

Use cases: - Semantic search - Similar documents find karna

------------------------------------------------------------------------

## 🗃️ Vector Database kya hota hai?

Ye database embeddings store karta hai aur similar data find karta hai.

Popular tools: - Pinecone (cloud) - FAISS (local) - Weaviate (hybrid
search) - Milvus (large scale)

------------------------------------------------------------------------

## ✂️ Chunking (Text ko todna)

Large documents ko chhote parts me todna padta hai.

### Types:

1.  Fixed chunk (e.g. 500 tokens)
2.  Recursive (heading → paragraph → sentence)
3.  Overlap (thoda repeat data)

### Example:

FAQ: Q1 + A1 = chunk 1\
Q2 + A2 = chunk 2

------------------------------------------------------------------------

## 🔁 RAG Pipeline

1.  User question aata hai
2.  Uska embedding banta hai
3.  Vector DB me search hota hai
4.  Top-k chunks milte hain
5.  Prompt me inject karte hain
6.  LLM final answer deta hai

------------------------------------------------------------------------

## ⚙️ Hybrid Search

2 cheeze combine karte hain: - Semantic (meaning based) - Keyword (exact
match)

Example: "Model X123 battery issue"

👉 "X123" ke liye keyword important hai\
👉 "battery issue" ke liye semantic

------------------------------------------------------------------------

## ✅ Evaluation kaise karein?

Metrics: - Hit Rate → sahi chunk mila ya nahi - Faithfulness → answer
context se hi hai ya nahi - Human Eval → banda check kare

------------------------------------------------------------------------

## ❌ Common Problems

1.  Bad chunking → important info split ho jata hai\
2.  Wrong retrieval → irrelevant data\
3.  Context overflow → important data cut ho jata hai\
4.  Hallucination → model khud ka answer bana deta hai

------------------------------------------------------------------------

## 🔍 Real Use Cases

### 1. Customer Support Bot

Product manuals se answer deta hai

### 2. Legal Q&A

Case laws retrieve karta hai

### 3. Company Internal Chatbot

Notion / Docs se data fetch karta hai

------------------------------------------------------------------------

## 🚀 TL;DR

-   RAG = Retrieval + Generation
-   Embeddings = text → vector
-   Vector DB = store + search
-   Chunking = text split
-   Pipeline = retrieve → inject → generate
-   Hybrid search = best accuracy

------------------------------------------------------------------------

## 💡 Final Samajh

LLM akela sab kuch nahi jaanta\
RAG use "Google + Brain" bana deta hai 😄
