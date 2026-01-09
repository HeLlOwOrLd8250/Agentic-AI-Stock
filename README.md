Autonomous Financial Decision Engine with Human Oversight

A stateful, agentic AI system that autonomously retrieves market data, analyzes news sentiment, and proposes financial actions using LangGraph, with Human-in-the-Loop (HITL) safety controls and full execution observability via LangSmith.

🚀 Key Features

Agentic Decision Making
Uses a graph-based orchestration engine to reason over stock prices, market sentiment, and user intent across multiple conversation turns.

Human-in-the-Loop (HITL) Safety
High-risk actions (e.g., stock purchases) are paused and require explicit human approval before execution.

Search-Based Sentiment Analysis
Retrieves recent financial news via search tools and performs LLM-driven sentiment analysis to influence decision confidence.

Stateful Conversations
Maintains full chat history across turns using checkpointed memory, enabling context-aware financial decisions.

End-to-End Observability
Integrated with LangSmith to trace agent reasoning steps, tool calls, sentiment outputs, and failure points.

🏗️ System Architecture

User → LangGraph Agent → Tools → Decision → HITL Approval → Action

Core Components

LLM Node (reasoning + tool selection)

Tool Nodes (stock price fetch, search, purchase simulation)

HITL Interrupts (approve / reject execution)

Memory Checkpointing (conversation persistence)

LangSmith Tracing (monitoring & debugging)

🛠️ Tech Stack

Language: Python

Agent Orchestration: LangGraph

LLM Framework: LangChain

Monitoring & Tracing: LangSmith

APIs: Alpha Vantage (stocks), Web Search APIs

Runtime: CLI (easily extendable to FastAPI)

🔄 How It Works

User asks about a stock or trading action

Agent retrieves real-time stock data

Agent searches recent news and analyzes sentiment

Agent reasons over price + sentiment

If action is risky → HITL approval required

Decision is executed or cancelled

Entire flow is logged and traceable

▶️ Running the Project
1️⃣ Install Dependencies
pip install langgraph langchain langsmith python-dotenv requests

2️⃣ Set Environment Variables
OPENAI_API_KEY=your_key_here
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langsmith_key

3️⃣ Run the Agent
python backend.py

4️⃣ Example Interaction
You: Should I buy TSLA?
Bot: TSLA is trading at $XXX. Recent news sentiment is positive.
HITL: Approve buying 10 shares of TSLA? (yes/no)

🔐 Safety & Reliability

No autonomous execution without human approval

Explicit confidence checks before action proposals

Full audit trail of decisions and tool usage

📈 What This Demonstrates

Agentic AI system design

Stateful backend orchestration

Tool-calling LLM workflows

Human-in-the-loop safety patterns

Production-grade observability

🧪 Future Improvements

Persistent storage (Redis / PostgreSQL)

Sentiment confidence scoring

Risk thresholds & policy engines

FastAPI deployment

Multi-agent planning & review roles
