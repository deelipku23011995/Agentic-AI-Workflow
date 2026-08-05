# Agentic AI Notes

## Agent Loop

```text
while goal_not_completed:

    think()

    choose_action()

    execute_tool()

    observe()

    update_memory()

    reflect()
```

---

# Search Strategies

## BFS (Breadth-First Search)

* Explores the state space level by level.
* Guarantees the shortest path is found first.

## DFS (Depth-First Search)

* Explores one branch as deep as possible before backtracking.

---

# Tool Calling Failure

When a tool call fails:

1. Log the exception.
2. Reflect on the error.
3. Retry if appropriate.
4. Escalate to Human-in-the-Loop (HITL) if unresolved.
5. Validate tool output before proceeding.

---

# Output Validation

* Structured Output
* LLM Judge
* Gold Standard Evaluation (for tasks like essay generation)

---

# Memory Explosion

## Context Window Memory (LLM Token Cap)

### Message Trimming

* Keep a fixed rolling window of the last **N** turns.
* Drop older middle conversation history.

### Tool Result Scrubbing

* Remove raw JSON/HTML tool outputs after extracting required information.

### Running Summarization

* Compress long conversations into a lightweight summary.

### Vector Offloading (RAG)

* Store long-term memory in a vector database.
* Retrieve only top-**k** relevant chunks when needed.

---

# RAG + Agent

* Agent analyzes intermediate results.
* Reformulates queries.
* Executes follow-up searches across multiple data sources.
* Stops only when sufficient context is gathered.

RAG provides:

* Private documents
* Schemas
* Current data

This enables accurate tool selection and decision-making.

---

# Multi-Hop Retrieval

Multi-hop retrieval solves queries that require multiple sequential retrieval steps.

## Example

### Hop 1 (Entity Resolution)

**Query:** Who directed *Inception*?

**Retrieved Context:** Christopher Nolan

### Hop 2 (Attribute Lookup)

**Query:** Where was Christopher Nolan born?

**Retrieved Context:** London, United Kingdom

---

# Solution

* Agentic Loop (ReAct Framework)
* Query Decomposition / Sub-Question Planning

---

# Agent Observability

* Tracing in OpenAI

---

# Prompt Injection

Prompt Injection is a cybersecurity vulnerability unique to Large Language Models (LLMs) and AI agents.

## Mitigation

* Architectural Separation

  * Use multi-agent architectures.

* Input & Output Sanitization

  * Filter incoming text for known malicious patterns.

---

# Token Budget Optimization & Cost

* Max Step Cap
* Context summarization for long conversations
* KV Cache to reuse attention states across requests
* Dynamic model routing (small → large)
