# 🦜 Learn LangChain (V1)

Welcome to the **LangChain V1 Learning Repository**! This repository serves as a hands-on, step-by-step guide to mastering the fundamentals of **LangChain V1** and building structured, agentic AI workflows.

Whether you are looking to integrate different model providers, parse structured outputs, build custom tools, or configure middleware for advanced agent behaviors, this repository provides interactive Jupyter Notebook examples for each concept.

---

## 📂 Repository Structure & Overview

All core learning notebooks are organized inside the [updatedlangchain/](updatedlangchain/) directory. Below is a breakdown of what you will find in each file:

| Notebook | Focus Area | Key Concepts Covered |
| :--- | :--- | :--- |
| 🚀 **[langchainintro.ipynb](updatedlangchain/langchainintro.ipynb)** | Introduction | Getting started with LangChain V1, library structure, and basic setups. |
| 💬 **[messages.ipynb](updatedlangchain/messages.ipynb)** | Prompting & Context | Core message types (System, User, AI), Metadata, Text Prompts, and Message Prompts. |
| 🎛️ **[modelintegration.ipynb](updatedlangchain/modelintegration.ipynb)** | LLM Provider Integration | Interacting with **OpenAI**, **Google Gemini**, and **Groq**. Features real-time output **Streaming**. |
| 📋 **[structuredoutput.ipynb](updatedlangchain/structuredoutput.ipynb)** | Output Parsing & Schemas | Restricting outputs to target schemas using **Pydantic** (nested), **TypedDict**, and **Data Classes**. |
| 🛠️ **[tools.ipynb](updatedlangchain/tools.ipynb)** | Function/Tool Calling | Binding external tools to LLMs, custom tool schemas, and tools execution loops. |
| 🧠 **[middleware.ipynb](updatedlangchain/middleware.ipynb)** | Agent Middleware & Control | Controlling execution loops, tracking behavior, and **Summarization Middleware** (token/fraction-based truncation). |

---

## 📖 In-Depth Notebook Walkthroughs

### 1. 🚀 [Introduction to LangChain](updatedlangchain/langchainintro.ipynb)
A gentle entry point to LangChain V1. This notebook shows you how to initialize basic chains, configure environment variables, and verify your installation.

### 2. 💬 [Messages & Context Management](updatedlangchain/messages.ipynb)
Learn how models perceive history and system guidelines.
* **Text Prompts**: Simple strings for single, standalone requests.
* **Message Prompts**: List of structured messages containing:
  * **Role**: Identifies who sent the message (System, User, Assistant).
  * **Content**: The core payload (text, images, or documents).
  * **Metadata**: Optional fields like message IDs and token usage stats.

### 3. 🎛️ [Models Integration & Streaming](updatedlangchain/modelintegration.ipynb)
Explore cross-provider compatibility and responsiveness.
* **Multi-Provider Setup**: Configure APIs for OpenAI (`gpt-4o`/`gpt-5`), Google Gemini, and Groq (`qwen-32b`).
* **Streaming Responses**: Utilize `.stream()` to yield and display output chunks progressively, improving UX for long-generation tasks.

### 4. 📋 [Structured Output Schemas](updatedlangchain/structuredoutput.ipynb)
Force the model to respond in a strict format matching a programmatically usable schema.
* **Pydantic Models**: Leverage rich type-safety, field descriptions, validation rules, and nested architectures.
* **TypedDict**: A lighter alternative using Python's typing system for when runtime validation isn't strictly necessary.
* **Data Classes**: Python-native `@dataclass` structures for simple representation.

### 5. 🛠️ [Tool Calling & Loops](updatedlangchain/tools.ipynb)
Teach your models to take action in the real world.
* **Defining Custom Tools**: Wrap Python functions using the `@tool` decorator to define inputs, schemas, and docstrings.
* **Tool Execution Loops**: Enable models to recognize when a tool should be run, receive the payload, execute it, and inject the result back into the context.

### 6. 🧠 [Agent Middleware & Advanced Controls](updatedlangchain/middleware.ipynb)
Control the execution loops of agents with custom middleware.
* **Summarization Middleware**: Automatically compress and summarize older conversation history when approaching context window token limits.
* **Token/Fraction Triggers**: Set triggers (`"tokens"`, `"messages"`) to maintain core instructions and recent context while compressing the rest.

---

## ⚙️ Setup & Installation

This project is managed using `uv` (recommended) or standard `pip`. 

### 1. Clone the Repository
```bash
git clone https://github.com/Anonymous-0143/Learn-Langchain.git
cd Learn-Langchain
```

### 2. Set Up Virtual Environment & Dependencies

**Using `uv`:**
```bash
uv venv
uv pip install -r requirements.txt
```

**Using standard `pip`:**
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Configure API Keys
Create a `.env` file in the root directory:
```env
OPENAI_API_KEY="your-openai-api-key"
GROQ_API_KEY="your-groq-api-key"
GEMINI_API_KEY="your-gemini-api-key"
```

Start your Jupyter environment and open the notebooks to begin learning!
```bash
jupyter lab
```
