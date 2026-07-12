# PS20 — Startup Blueprint Generator Agent

> **AICTE IBM SkillsBuild Summer Internship Program (SIP) 2026**  
> Organised by **Edunet Foundation** in collaboration with **IBM**

---

## Project Overview

Aspiring entrepreneurs often struggle to turn a raw startup idea into a structured, actionable business plan — information on market research, funding, government schemes, and legal requirements is scattered across unreliable sources. This project builds an **agentic AI system** using **IBM watsonx Orchestrate** and **IBM Granite models**, powered by **Retrieval-Augmented Generation (RAG)**, to transform a simple startup idea into a complete, structured business blueprint — eliminating ambiguity and accelerating the journey from idea to implementation.

---

## Problem Statement

**PS No. 20 — Startup Blueprint Generator Agent**

Given a startup idea described in plain language, the agent retrieves relevant data from a curated knowledge base and generates a structured blueprint covering:

| Section | Description |
|---|---|
| 📝 Idea Summary | Problem-solution fit for the given idea |
| 🧩 Business Model Canvas | All 9 BMC blocks tailored to the idea |
| 📊 Market & Competitor Snapshot | Market context and competitor landscape |
| 💰 Estimated Budget | 6-month runway estimate by category |
| 💵 Revenue Model | Best-fit monetization model(s) with reasoning |
| 🚀 Go-to-Market Strategy | Positioning, channels, launch plan, early metrics |
| 🏛️ Government Schemes | Relevant Startup India / MSME / state schemes |
| ⚖️ Legal & Compliance Checklist | Registration type, GST, IP, founder agreements |
| 🤝 Investor Connections | Relevant investor types and funding-stage guidance |

---

## Knowledge Base

- **Source:** Curated reference documents (government portals, incubator databases, policy documents)
- **Format:** Text documents uploaded to the agent's Knowledge (RAG) store
- **Size:** ~4 core documents, well within the platform's 30MB knowledge base limit

### Documents Used

| Document | Description |
|---|---|
| Government Schemes | Startup India, MSME, state-level schemes and incubation benefits |
| Funding & Investor Directory | Angel networks, VC firms, incubators, funding-stage guidance |
| Legal & Compliance Checklist | Business registration types, GST, IP, founder agreements |
| Business Frameworks | Business Model Canvas, revenue models, go-to-market templates |

---

## Solution Approach

Built using **IBM watsonx Orchestrate — Agent Builder** (no-code agent configuration):

1. Created a new agent, **Startup Blueprint Generator AI**, with a description defining its purpose and scope
2. Configured **Knowledge (RAG)** by uploading the four curated reference documents
3. Set the foundation model to an **IBM Granite** model for reasoning and generation
4. Wrote **Behavior instructions** enforcing a consistent 9-section blueprint output structure
5. Added **Guidelines** (guardrails) to prevent fabricated scheme/investor details, keep responses structured, redirect off-topic queries, and disclaim legal/financial advice
6. Configured a **welcome message** and **quick-start prompts** for the chat interface
7. Optionally added an **Exa MCP toolset** (`web_search_exa`, `web_fetch_exa`) for live market and competitor research
8. Tested the agent in debug mode with sample startup ideas
9. **Deployed** the agent via the Home page channel on watsonx Orchestrate

---

## Agent Capabilities & Testing

| Aspect | Details |
|---|---|
| **Reasoning Style** | ReAct (Reasoning + Acting) — plans retrieval and generation steps before responding |
| **Grounding** | All funding, legal, and scheme details are grounded in the uploaded knowledge base |
| **Guardrails** | 4–5 guidelines covering fabrication prevention, structure, off-topic redirection, and legal disclaimers |
| **Output Structure** | Consistent 9-section blueprint for every startup idea submitted |
| **Sample Ideas Tested** | Organic snack subscription box (Pune); college tutoring marketplace app |

---

## Technology Stack

| Component | Tool |
|---|---|
| Cloud Platform | IBM Cloud Lite |
| Agent Platform | IBM watsonx Orchestrate — Agent Builder |
| Foundation Model | IBM Granite (e.g. granite-3-8b-instruct) |
| Retrieval | Retrieval-Augmented Generation (RAG) — Knowledge (Upload Files) |
| Model Testing | IBM watsonx.ai — Prompt Lab |
| Optional Tooling | Exa MCP Server (`web_search_exa`, `web_fetch_exa`) |

---

## Repository Structure

```
PS20_Startup_Blueprint_Generator/
│
├── Government_Schemes_India.txt          # RAG knowledge document
├── Funding_Investor_Directory.txt        # RAG knowledge document
├── Legal_Compliance_Checklist.txt        # RAG knowledge document
├── BMC_Revenue_GTM_Templates.txt         # RAG knowledge document
├── Problem_Statement_PS20.pdf            # Problem statement document
├── Startup_Blueprint_Generator.pptx      # Project submission PPT
└── README.md                             # This file
```

---

## How to Reproduce

### Step 1 — Set Up IBM Cloud
1. Create a free IBM Cloud Lite account at [cloud.ibm.com](https://cloud.ibm.com)
2. Provision a **watsonx Orchestrate** instance (trial/Lite)
3. Provision a **watsonx.ai** instance for Granite model access via Prompt Lab

### Step 2 — Create the Agent
1. In watsonx Orchestrate, go to **Manage agents → Create agent**
2. Name it `Startup Blueprint Generator AI`
3. Add a **Profile** description covering purpose, technology, and outputs

### Step 3 — Configure Knowledge (RAG)
1. Go to the **Knowledge** tab → **New Knowledge → Upload files**
2. Upload the four reference documents (schemes, funding, legal, BMC/GTM templates)
3. Add a description explaining when the agent should use this knowledge

### Step 4 — Configure Behavior & Guidelines
1. Go to **Behavior** → paste system instructions enforcing the 9-section blueprint structure
2. Go to **Guidelines** → add guardrail rules (no fabrication, structured output, off-topic redirect, legal disclaimer)
3. Set **Agent style** to ReAct for multi-step reasoning

### Step 5 — Test & Deploy
1. Use **Test agent** / debug mode chat to try sample startup ideas
2. Verify the response follows the full 9-section structure and cites knowledge-grounded facts
3. Click **Deploy** to publish the agent on the Home page channel

---

## Internship Details

| Field | Details |
|---|---|
| **Program** | AICTE IBM SkillsBuild Summer Internship Program 2026 |
| **Student** | Anshul Pravin Bhusal |
| **Email** | 202501040341@mitaoe.ac.in |
| **Institution** | MIT Academy of Engineering (MIT AOE), Pune |
| **Branch** | B.Tech Computer Engineering |
| **Problem Statement** | PS 20 — Startup Blueprint Generator Agent |

---

## Acknowledgements

- **IBM** for providing the watsonx Orchestrate and watsonx.ai platforms and IBM Cloud Lite access
- **Edunet Foundation** for organizing the AICTE SIP program
- **AICTE** for facilitating the internship program

---

*Built with IBM watsonx Orchestrate and IBM Granite — Agentic AI powered by Retrieval-Augmented Generation*
