# Advanced Multi-Agentic RAG System

A powerful, production-ready multi-agent Retrieval-Augmented Generation (RAG) application built with Streamlit, LangChain, and Groq LLMs. This project demonstrates a modular, self-correcting workflow for answering user queries using both internal knowledge sources and real-time web search, with built-in fact-checking and safety mechanisms.

## Key Features

- **Multi-Agent Workflow:** Modular agents for routing, retrieval, query reformulation, web search, synthesis, answer generation, fact-checking, and safety checking
- **Hybrid Knowledge Sources:** Supports both uploaded files (PDF, DOCX, TXT) and URLs as knowledge bases, with fallback to default sources
- **Dynamic Query Handling:** Automatically routes queries to the best agent (internal retrieval, web search, clarification, etc.) based on context
- **Self-Correction:** Reformulates queries and retries retrieval before falling back to web search
- **Fact-Checking:** Extracts factual claims from generated answers and verifies them using real-time web search
- **Safety Checking:** Analyzes generated content for harmful or inappropriate material and revises or blocks unsafe responses
- **Interactive UI:** Streamlit-based chat interface with workflow visualization, logs, and configuration sidebar
- **Configurable Parameters:** Easily adjust chunk size, retriever top-K, and LLM temperature from the sidebar

## Architecture & Workflow

\\\mermaid
flowchart TD
    Start([Start]) --> Router
    Router -->|retrieve| Retriever
    Router -->|reformulate| Reformulator
    Router -->|web_search| WebSearcher
    Router -->|clarify| Clarifier
    Router -->|generate| Generator
\\\

The system employs intelligent routing to determine the best approach for each query:
- **Retrieval Agent:** Searches internal knowledge base
- **Reformulator:** Improves query quality for better results
- **Web Search Agent:** Fetches real-time information from the web
- **Generator:** Creates comprehensive answers
- **Fact Checker:** Verifies claims for accuracy
- **Safety Checker:** Ensures content safety and appropriateness

## Installation & Setup

\\\ash
# Clone the repository
git clone https://github.com/niftydiran-ui/multi-agentic-rag.git
cd multi-agentic-rag

# Install dependencies
pip install -r requirements.txt

# Set up environment variables (Groq API key, etc.)
# Add your API keys to .env file

# Run the application
streamlit run app.py
\\\

## Tech Stack

- **LangChain:** Agent orchestration and RAG pipeline
- **Groq LLMs:** Fast inference for multi-agent workflows
- **Streamlit:** Interactive web interface
- **FAISS/Chroma:** Vector database for embeddings
- **Web Search APIs:** Real-time fact verification

## Use Cases

- Enterprise knowledge management with fact-checking
- Research assistants with web search fallback
- Customer support with safety guardrails
- Educational platforms requiring verified information
- Any application needing reliable, source-attributed answers

Perfect for building production-grade RAG systems that prioritize accuracy, safety, and user experience.
