# Episodic AI

> A Graph-Based Episodic Memory System for Long-Horizon AI Agents

Episodic AI is a memory-centric agent framework that enables Large Language Models (LLMs) to build, organize, and reason over long-term conversational experiences.

Unlike traditional Retrieval-Augmented Generation (RAG) systems that retrieve isolated text chunks, Episodic AI reconstructs memories as interconnected episodes, people, events, topics, and timelines. This allows agents to perform temporal reasoning, relationship tracking, memory reconstruction, and multi-hop retrieval across thousands of dialogue turns.

---

## Why Episodic AI?

Current AI assistants struggle with long-term memory.

Most systems:

* Store information as independent vector embeddings.
* Lose temporal relationships between events.
* Fail to reason across multiple conversations.
* Retrieve relevant facts but not coherent memories.

Episodic AI addresses these limitations through a graph-structured memory architecture inspired by human episodic memory.

The system transforms conversations into structured memory episodes and enables agents to reconstruct experiences rather than simply retrieve documents.

---

## Core Architecture

```text
User Conversations
        │
        ▼
┌─────────────────┐
│ Memory Rewrite  │
│ & Normalization │
└─────────────────┘
        │
        ▼
┌─────────────────┐
│ Embedding Layer │
└─────────────────┘
        │
        ▼
┌─────────────────┐
│ Keyword & Event │
│ Extraction      │
└─────────────────┘
        │
        ▼
┌─────────────────┐
│ Graph Memory    │
│ Construction    │
└─────────────────┘
        │
        ▼
┌─────────────────┐
│ Memory Tools    │
│ Retrieval Layer │
└─────────────────┘
        │
        ▼
┌─────────────────┐
│ Agentic Reasoning│
└─────────────────┘
        │
        ▼
       Answer
```

---

## Key Features

### Graph-Based Memory

Stores memories as connected entities:

* People
* Events
* Topics
* Conversations
* Time references
* Relationships

### Episodic Reconstruction

Instead of retrieving isolated chunks, the system reconstructs contextual episodes from multiple related memories.

### Temporal Reasoning

Supports:

* Event ordering
* Timeline reconstruction
* Date reasoning
* Relative-to-absolute time conversion

### Multi-Hop Memory Search

The agent can iteratively query memory tools to discover information through multiple reasoning steps.

### Long-Horizon Context

Designed for conversations spanning:

* Multiple sessions
* Thousands of turns
* Long-term user interactions

### OpenRouter Integration

Supports state-of-the-art LLMs through OpenRouter:

* Gemini 2.5 Flash
* Gemini 2.5 Pro
* DeepSeek V4 Flash
* DeepSeek V4
* Qwen 3
* Claude Models
* GPT Models

---

## Memory Pipeline

### Stage 1: Rewrite

Raw dialogue is transformed into self-contained memory units.

Example:

```text
Original:
"He bought it yesterday."

Rewritten:
"John bought a bicycle on 2025-06-05."
```

### Stage 2: Embedding

Memory units are converted into dense vector representations for semantic retrieval.

### Stage 3: Knowledge Extraction

The system extracts:

* Entities
* Topics
* Personal facts
* Relationships
* Events
* Temporal references

### Stage 4: Graph Construction

Memories are connected into a structured memory graph.

### Stage 5: Agentic Reasoning

An LLM-driven agent performs:

* Tool calling
* Memory search
* Evidence collection
* Multi-step reasoning
* Answer generation

---

## Example Memory Retrieval

Question:

```text
What gift did Sarah receive before moving to New York?
```

Agent Workflow:

```text
Search Person → Sarah
        │
        ▼
Find Related Events
        │
        ▼
Locate Move Event
        │
        ▼
Trace Previous Episode
        │
        ▼
Retrieve Gift Information
        │
        ▼
Generate Answer
```

---

## Technology Stack

### LLM Layer

* OpenRouter
* OpenAI SDK

### Memory Layer

* Graph Memory System
* Episodic Memory Controller
* Temporal Event Index

### Retrieval Layer

* Semantic Embeddings
* Hybrid Search
* LLM Re-Ranking

### Agent Layer

* Tool Calling
* Iterative Reasoning
* Multi-Step Planning

### Evaluation

* Exact Match
* F1 Score
* LLM-as-a-Judge Evaluation

---

## Installation

```bash
git clone <your-repository-url>

cd Episodic-AI

python -m venv venv

source venv/bin/activate
```

Install dependencies:

```bash
pip install openai torch numpy tqdm requests regex jsonschema nltk bert_score python-dotenv
```

---

## Environment Variables

Create a `.env` file:

```env
OPENROUTER_API_KEY=your_openrouter_key
```

---

## Run

```bash
python run.py --data locomo --model gemini --file test
```

Single sample:

```bash
python run.py --data locomo --model gemini --file test --sample 42
```

---

## Research Motivation

Human memory is not a database lookup.

When recalling information, people reconstruct experiences by connecting events, people, places, and timelines.

Episodic AI applies the same principle to LLM agents through graph-based memory reconstruction and agentic reasoning.

The goal is to move beyond traditional RAG systems toward memory-native AI agents capable of long-term contextual understanding.

---

## Future Roadmap

* Persistent user memory
* Multi-agent memory sharing
* Knowledge graph expansion
* Real-time memory updates
* Memory compression
* Lifelong learning agents
* Personal AI companions
* Enterprise knowledge memory systems

---

## License

MIT License

---

## Citation

If you use Episodic AI in your research or projects, please cite the repository and acknowledge the original academic inspirations that motivated graph-based memory systems.
