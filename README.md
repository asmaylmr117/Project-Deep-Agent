# 🧠 Deep Agents

<p align="center">
  <strong>Building intelligent, autonomous AI agents with LangChain Deep Agents</strong>
</p>

<p align="center">
  <a href="https://github.com/asmaylmr117/Deep-Agent">
    <img src="https://img.shields.io/github/stars/asmaylmr117/Deep-Agent?style=for-the-badge&logo=github" alt="GitHub Stars">
  </a>
  <a href="https://github.com/asmaylmr117/Deep-Agent">
    <img src="https://img.shields.io/github/forks/asmaylmr117/Deep-Agent?style=for-the-badge&logo=github" alt="GitHub Forks">
  </a>
  <img src="https://img.shields.io/badge/Python-3.11--3.14-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/LangChain-Deep%20Agents-1C3C3C?style=for-the-badge" alt="LangChain">
  <img src="https://img.shields.io/badge/LangSmith-Observability-FF6B35?style=for-the-badge" alt="LangSmith">
</p>

---

## 📖 About

**Deep Agents** is a hands-on project for exploring and building advanced AI agents using the **LangChain Deep Agents** ecosystem.

The project follows the concepts and practical exercises from the **LangChain Academy Deep Agents course**, covering agent architecture, planning, tool usage, context management, sub-agents, and AI workflows.

The repository is organized into multiple modules (`m1` → `m5`), allowing each concept to be explored independently.

---

## ✨ What You'll Learn

* 🤖 Building autonomous AI agents
* 🧠 Agent planning and task decomposition
* 🔧 Tool calling and tool integration
* 👥 Working with sub-agents
* 🌐 Web search and external tools
* 📂 File and context management
* 📊 LLM observability with LangSmith
* 🔄 Multi-step AI workflows
* 🧩 Deep Agents architecture
* 🛠️ Building reusable agent components

---

## 🏗️ Project Structure

```text
Deep-Agent/
│
├── m1/                         # Module 1
├── m2/                         # Module 2
├── m3/                         # Module 3
├── m4/                         # Module 4
├── m5/                         # Module 5
│
├── models.py                   # Model configuration
├── env_utils.py                # Environment configuration utilities
├── pyproject.toml              # Project dependencies & configuration
├── uv.lock                     # Locked dependencies
├── .gitignore
└── README.md
```

---

## 🛠️ Tech Stack

| Technology         | Purpose                                      |
| ------------------ | -------------------------------------------- |
| 🐍 **Python**      | Core programming language                    |
| 🧠 **LangChain**   | LLM and agent framework                      |
| 🤖 **Deep Agents** | Agent architecture and capabilities          |
| 📊 **LangSmith**   | Tracing, debugging and observability         |
| 🔎 **Tavily**      | Web search capabilities                      |
| ⚡ **uv**           | Fast Python package & environment management |

---

## ⚙️ Requirements

Before getting started, make sure you have:

* **Python 3.11 – 3.14**
* **uv**
* An API key for your preferred LLM provider
* **LangSmith API key**
* **Tavily API key** *(optional, used for web-search functionality)*

Windows users can run the project through **WSL** if required.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/asmaylmr117/Deep-Agent.git
cd Deep-Agent
```

### 2. Create the environment

Using `uv`:

```bash
uv sync
```

This installs the required dependencies and creates the project's virtual environment.

---

### 3. Configure environment variables

Create a `.env` file in the project directory.

```env
# LangSmith
LANGSMITH_API_KEY=your-langsmith-api-key
LANGSMITH_TRACING=true
LANGSMITH_PROJECT=deep-agent

# LLM Provider
ANTHROPIC_API_KEY=your-anthropic-api-key

# Optional providers
# OPENAI_API_KEY=your-openai-api-key
# GOOGLE_API_KEY=your-google-api-key

# Optional - Web Search
TAVILY_API_KEY=your-tavily-api-key
```

> ⚠️ Never commit your `.env` file or expose API keys publicly.

---

## 🔍 Verify Your Setup

Run:

```bash
uv run python env_utils.py
```

The script checks whether your required environment variables are available.

If a variable shows:

```text
<not set>
```

check your `.env` configuration.

---

## ▶️ Running the Project

Use `uv run` to execute Python modules while automatically using the project's environment.

For example:

```bash
uv run python m1/...
```

Replace the path with the appropriate script inside each module.

You can explore the modules sequentially:

```text
m1 → m2 → m3 → m4 → m5
```

Each module builds on the concepts introduced previously.

---

## 📊 LangSmith

This project uses **LangSmith** for tracing and observing agent execution.

Enable tracing in `.env`:

```env
LANGSMITH_TRACING=true
LANGSMITH_API_KEY=your-api-key
LANGSMITH_PROJECT=deep-agent
```

LangSmith allows you to inspect:

* Agent execution
* LLM calls
* Tool calls
* Execution traces
* Errors
* Latency
* Agent behavior

If you don't want tracing, you can disable it:

```env
LANGSMITH_TRACING=false
```

---

## 🔎 Tavily Web Search

Some modules can use Tavily to provide web-search capabilities.

Add your API key:

```env
TAVILY_API_KEY=your-tavily-api-key
```

If Tavily is not configured, modules that depend on web search may not provide their full functionality.

---

## 🧠 Deep Agent Architecture

A Deep Agent can be thought of as a system composed of several capabilities:

```text
                    ┌───────────────────┐
                    │     User Task     │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │    AI Agent       │
                    │   Orchestrator    │
                    └─────────┬─────────┘
                              │
              ┌───────────────┼───────────────┐
              ▼               ▼               ▼
        ┌──────────┐    ┌──────────┐    ┌──────────┐
        │ Planning │    │  Tools   │    │ Context  │
        └──────────┘    └──────────┘    └──────────┘
              │               │               │
              └───────────────┼───────────────┘
                              ▼
                    ┌───────────────────┐
                    │   Sub-Agents      │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │     Final Result  │
                    └───────────────────┘
```

The goal is to move beyond simple chatbot interactions and create agents capable of handling **long-running, multi-step tasks**.

---

## 📚 Learning Path

The repository is organized as a progressive learning path:

### Module 1 — Foundations

Introduction to Deep Agents and the basic agent architecture.

### Module 2 — Planning

Exploring how agents break complex tasks into smaller steps and manage progress.

### Module 3 — Tools & Context

Working with tools, external capabilities, and context management.

### Module 4 — Research Agents

Building agents capable of gathering information and performing research using external tools.

### Module 5 — Advanced Agent Workflows

Combining the concepts into more advanced agentic workflows.

---

## 🔐 Security

Never commit API keys to GitHub.

Make sure `.env` is included in `.gitignore`:

```gitignore
.env
.env.*
!.env.example
```

If an API key has accidentally been pushed to GitHub, revoke it immediately and generate a new one.

---

## 🎯 Project Goals

This project aims to provide practical experience with modern **Agentic AI** development, including:

* Autonomous agents
* Tool-using agents
* Agent planning
* Sub-agent architectures
* Context management
* AI workflows
* LLM observability
* Multi-step reasoning systems

---

## 🌱 Future Improvements

Possible future additions include:

* [ ] Add more specialized sub-agents
* [ ] Integrate MCP servers
* [ ] Add persistent agent memory
* [ ] Add human-in-the-loop workflows
* [ ] Add more external tools
* [ ] Build a web interface
* [ ] Add automated evaluations
* [ ] Deploy agents to production
* [ ] Add more advanced multi-agent workflows

---

## 📚 Resources

* **LangChain Academy — Deep Agents**
* **LangChain Documentation**
* **LangGraph Documentation**
* **LangSmith**
* **Tavily**

---

## 👨‍💻 Author

**Mostafa Ismail El-Anani**

Full Stack Developer & AI Agent Developer

Interested in:

* Full Stack Development
* Artificial Intelligence
* AI Agents
* LangChain
* LangGraph
* MCP
* Multi-Agent Systems

---

## ⭐ Support

If you find this project useful, consider giving it a ⭐ on GitHub.

<p align="center">
  <strong>Built with 🧠 and 🤖</strong>
</p>
