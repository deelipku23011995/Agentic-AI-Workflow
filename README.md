# Multi-Agent Workflow & Tool Systems with OpenAI Agents SDK & Qwen 3

A hands-on notebook demonstration showcasing how to construct production-ready multi-agent systems using the **OpenAI Agents SDK** powered by open-source models like **Qwen3-8B** (hosted locally or via open-weights inference endpoints).

This repository covers key concepts including tool calling, structured outputs, SQLite session memory management, multi-agent workflows, handoffs, and agent guardrails.

---

## 🌟 Key Features

* **Open-Source LLM Integration:** Powered by **Qwen3-8B** using OpenAI-compatible APIs (vLLM, Ollama, LM Studio, or Hugging Face TGI).
* **Tool Integration:** Equipping agents with Python functions and custom tools to perform action-oriented tasks.
* **Structured Outputs:** Enforcing schema-validated responses (JSON/Pydantic) directly from open-weights models.
* **Session & Memory Management:** Native multi-turn state persistence powered by built-in **SQLite** session backends.
* **Multi-Agent Orchestration & Handoffs:** Routing tasks between specialized sub-agents and using agents directly as tools.
* **Input & Output Guardrails:** Enforcing safety boundaries, schema compliance, and input/output validation across agent transfers.

---


## 🧪 Core Concepts Covered

### 1. Tool-Calling & Execution

Define custom Python functions and bind them to the Qwen3 model. The SDK automatically serializes inputs and handles tool call loops.

### 2. Structured Outputs

Enforce reliable response structures using Pydantic schema validation for deterministic parsing.

### 3. SQLite Memory Management

Persist conversation history, internal agent thoughts, and execution context across multiple turns using the built-in SQLite session manager.

### 4. Multi-Agent Workflows & Handoffs

* **Direct Handoffs:** Pass execution context from a coordinator/triage agent directly to specialized domain agents (e.g., Search Agent, Code Interpreter Agent).
* **Agent-as-a-Tool Pattern:** Wrap sub-agents as executable tools that return processed outputs back to the main caller.

### 5. Input & Output Guardrails

Wrap agent inputs and outputs with validation layers to sanitize prompts, prevent injection attacks, and guarantee compliance before emitting final answers.

---


Distributed under the [MIT License](https://www.google.com/search?q=LICENSE).
