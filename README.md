# Environmental Science RAG Pipeline

An experimental Retrieval-Augmented Generation pipeline built with LlamaIndex and Google Gemini to evaluate and optimize retrieval parameters for academic environmental science literature. 

This project systematically tests how variations in text chunking sizes, embedding models, and system prompts impact response accuracy, faithfulness, and synthesis capabilities.

---

## Core Experiments & Methodology

1. **Chunk Size Optimization**
   * Tested sizes: 256, 512, and 1024 tokens (with a 10% overlap).
   * Goal: Balance granular detail retrieval with broad context synthesis for complex questions.

2. **Embedding Model Comparison**
   * Tested encoders: `BAAI/bge-small-en` versus `all-MiniLM-L6-v2`.
   * Goal: Evaluate how open-source HuggingFace vector embedding models affect semantic search accuracy against specialized scientific text.

3. **Prompt Engineering & Guardrails**
   * Tested variations: Naive baseline, grounded refusal triggers, structured markdown tables, verbose citations, and concise tutor styles.
   * Goal: Mitigate hallucinations and enforce strict source adherence using custom system prompts.

---

## Tech Stack

* **LLM:** Google Gemini (`gemini-2.5-flash`) via the Google GenAI SDK
* **Orchestration:** LlamaIndex (`VectorStoreIndex`, `SentenceSplitter`, `SimpleDirectoryReader`)
* **Embeddings:** HuggingFace (`sentence-transformers`)
* **Demo Interface:** Gradio for interactive querying
* **Environment:** Google Colab / Python

---

## Quick Start

1. Clone the repository and install dependencies:
   ```bash
   pip install llama-index google-genai pypdf sentence-transformers llama-index-embeddings-huggingface llama-index-llms-google-genai gradio
