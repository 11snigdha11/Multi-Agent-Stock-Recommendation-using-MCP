# Model Context Protocol (MCP) & Multi-Agent Systems 

This repository explores the **Model Context Protocol (MCP)** introduced by Anthropic, which standardizes how AI models connect to external tools and data sources. It includes practical implementations ranging from basic real-time web search integrations to a complex, multi-agent AI supervisor system.



##  Overview

Large Language Models (LLMs) are incredibly powerful, but they suffer from two main limitations:
1. They lack access to real-time, post-training data.
2. They cannot execute actions (tasks) on their own.

**MCP solves this** by standardizing the client-server architecture for AI tools. This repository demonstrates how to build MCP clients that connect to MCP servers (like Bright Data for web scraping) to give LLMs real-time superpowers.

##  Projects Included

### 1. Basic MCP Integration (Real-Time Search)
A simple agent that connects to the Bright Data MCP Server to answer real-time queries that standard LLMs cannot answer (e.g., "Who won the IPL 2025?" or "Find flights from Bangalore to Delhi"). 

### 2. Multi-Agent Stock Recommendation System
An end-to-end, modular AI system built using **LangGraph Supervisor**. Instead of overwhelming a single LLM with multiple tasks, this system delegates responsibilities to specialized agents:
* ** Stock Finder Agent:** Identifies promising stocks (avoiding penny stocks).
* ** Market Data Agent:** Fetches current market prices and historical data.
* ** News Analyst Agent:** Scrapes recent news articles and classifies sentiment (Positive/Negative/Neutral).
* ** Price Recommender Agent:** Synthesizes all data to provide actionable Buy/Sell/Hold recommendations with target prices.
* ** Supervisor Agent:** Orchestrates the workflow and delegates tasks to the worker agents.

##  Tech Stack
* **Frameworks:** LangChain, LangGraph (for multi-agent orchestration)
* **Protocol:** Model Context Protocol (MCP) by Anthropic
* **LLM Provider:** OpenAI (GPT-4o or similar)
* **External Tools/Servers:** Bright Data (Web Scraping & Real-time search)
* **Language:** Python

## ⚙️ Prerequisites & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/11snigdha11/Multi-Agent-Stock-Recommendation-using-MCP
   cd STOCK RECOMMENDER

2.**Install Dependencies:**
Make sure you have Python installed, then run:

Bash
   pip install -r requirements.txt
(Note: Ensure you have langchain, langgraph, langchain-mcp-adapters, langchain-openai, and python-dotenv installed).

3.**Environment Variables:**
Create a .env file in the root directory and add your API keys:

Code snippet
   OPENAI_API_KEY=your_openai_api_key_here
   BRIGHT_DATA_API_TOKEN=your_bright_data_token_here
   # Optional depending on your Bright Data setup:
   BRIGHT_DATA_WEB_UNLOCKER_ZONE=your_zone_here 
4.**Usage:**
To run the multi-agent stock recommendation system, execute the main Python file:

Bash
python main.py
**Example Query handled by the system:**

"Give me a good stock recommendation from NSE."

The output will clearly show the workflow passing from the Supervisor to the specialized agents and finally outputting a comprehensive, data-backed stock analysis.

   