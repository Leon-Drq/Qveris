# **Qveris — The Tool OS for AI Agents**

### *One unified interface for every tool your AI will ever need.*

<p align="center">
  <img src="Qverislogo.jpg" width="160" />
</p>

<p align="center">
  <b>Qveris — The Tool OS for AI Agents</b><br/>
  <sub>One unified interface for every tool your AI will ever need.</sub>
</p>

<p align="center">
  <b>Language:</b>
  <b>🇺🇸 English</b> |
  <a href="README_zh-CN.md">🇨🇳 简体中文</a>
</p>

---

# 📘 Table of Contents

* [✨ Overview](#-overview)
* [💡 Why Qveris?](#-why-qveris)
* [🆘 Problems Qveris Solves](#-problems-qveris-solves)
* [🔧 Key Features](#-key-features)
* [🏗 Architecture](#-architecture)
* [⚡ Quickstart](#-quickstart)
* [🧰 Built-in Tools](#-built-in-tools)
* [⚔ Competitor Comparison](#-competitor-comparison)
* [🔌 Tool Schema Standard](#-tool-schema-standard)
* [🧠 Tool Routing Engine](#-tool-routing-engine)
* [🧩 Build Your Own Tools](#-build-your-own-tools)
* [🤖 Build an Agent](#-build-an-agent)
* [🛒 Marketplace](#-marketplace)
* [🔐 Enterprise](#-enterprise)
* [📦 SDKs](#-sdks)
* [📈 Pricing](#-pricing)
* [🚀 Roadmap](#-roadmap)
* [🤝 Contributing](#-contributing)
* [💬 Community](#-community)
* [❓ FAQ](#-faq)
* [⭐ Star Us](#-star-us)

---

# ✨ Overview

Qveris is the **Tool Operating System (Tool OS)** for AI Agents.

It standardizes how LLMs call tools — search engines, OCR services, PDF parsers, HTTP APIs, data providers, and business actions — through **a single unified tool interface**.

> **Qveris = Kubernetes + Homebrew + Zapier for Tool-Based AI.**

---

# 💡 Why Qveris?

Today's agents rely heavily on tools, but the ecosystem is fragmented:

* Inconsistent APIs
* Different JSON formats
* Custom auth
* No sandbox
* No routing or fallback
* No governance
* High integration cost

**Qveris unifies and abstracts everything.**

---

# 🆘 **Problems Qveris Solves**

### ❗ Current LLM tool-calling suffers from **four major pain points**:

| Problem                       | Description                                                                            |
| ----------------------------- | -------------------------------------------------------------------------------------- |
| ❌ **Ecosystem Fragmentation** | OpenAI, Kimi, Zhipu, Llama tools are incompatible and non-interoperable.               |
| ❌ **No Security Guarantees**  | Tools may access databases, APIs, file systems — high risk without sandboxing.         |
| ❌ **High Development Cost**   | Each tool requires custom integration, config, rate limit handling, logging & retries. |
| ❌ **Uncontrollable Behavior** | LLM actions are unpredictable; hard to trace execution or audit logs.                  |

---

### ✅ **Qveris Unified Solution**

| Solution                 | Description                                                                           |
| ------------------------ | ------------------------------------------------------------------------------------- |
| ⭐ **A Standard**         | All tools are wrapped as controllable, safe, structured executable modules (Q-Tools). |
| ⭐ **A Sandbox**          | Tools run inside isolated, controlled execution environments.                         |
| ⭐ **A Unified Protocol** | LLMs call, combine, and compose tools naturally via standardized schema.              |

---

# 🔧 Key Features

✔ Unified Tool Schema
✔ 200+ Tools
✔ Provider-agnostic Routing
✔ Sandbox Execution
✔ Tool Marketplace
✔ Agent Integration (GPT, LangChain, LlamaIndex, etc.)
✔ Enterprise Permissions & Audit Logs

---

# 🧰 **Built-in Tools (Preview)**

<p align="center">
<img src="https://dummyimage.com/1000x300/1a1a1a/ffffff&text=100%2B+built-in+tools" width="100%" />
</p>

Supported categories:

* Search (Google, Bing, Arxiv, DuckDuckGo...)
* OCR (Vision, PaddleOCR, Tesseract)
* PDF parsing
* Information Extraction
* Data (Weather, Finance, Crypto, News)
* HTTP universal wrapper
* Business automation tools (Email, Slack, CRM...)

---

# ⚔ **Competitor Comparison**

| Product               | Qveris | OpenAI Plugins | LangChain Tools | Kimi Tools |
| --------------------- | ------ | -------------- | --------------- | ---------- |
| **Openness**          | ⭐⭐⭐⭐⭐  | ⭐⭐⭐            | ⭐⭐⭐⭐            | ⭐          |
| **Security Sandbox**  | ⭐⭐⭐⭐⭐  | ⭐⭐             | ⭐               | ⭐⭐         |
| **Unified Protocol**  | ⭐⭐⭐⭐⭐  | ⭐              | ❌               | ❌          |
| **Tool Ecosystem**    | ⭐⭐⭐⭐⭐  | ⭐⭐             | ⭐⭐⭐⭐            | ⭐          |
| **LLM Compatibility** | ⭐⭐⭐⭐⭐  | ⭐              | ⭐⭐⭐⭐            | ❌          |

> **Qveris is the most complete tool invocation infrastructure available today.**

---

# 🏗 Architecture

```
+------------------------------------------------------+
|                    AI Model (LLM)                    |
|      GPT / Claude / Kimi / Llama / Grok / etc.      |
+------------------------+-----------------------------+
                         |
                         | Unified Tool Calls
                         |
+------------------------v-----------------------------+
|                  Qveris Tool OS                      |
| Routing · Sandbox · Logging · Schema · Billing · ACL |
+-----------+-------------------------+----------------+
            |                         |
     +------v-------+        +--------v--------+
     |  Built-in    |        |  Third-party    |
     |   Tools      |        |     Tools       |
     +--------------+        +-----------------+
```

---

# ⚡ Quickstart

### **1. Install**

```bash
npm install @qveris/sdk
```

or

```bash
pip install qveris
```

---

### **2. Initialize Client**

```ts
import { Qveris } from "@qveris/sdk";
const qv = new Qveris({ apiKey: process.env.QVERIS_KEY });
```

---

### **3. Call any tool**

```ts
const result = await qv.tools.search({
  query: "latest AI research trends"
});
console.log(result);
```

---

# 🔌 Tool Schema Standard

### Request

```json
{
  "action": "search",
  "input": {
    "query": "AI agents",
    "limit": 5
  }
}
```

### Response

```json
{
  "status": "ok",
  "data": [...]
}
```

---

# 🧠 Tool Routing Engine

Qveris auto-selects the best provider based on:

* Latency
* Success rate
* Cost
* Provider ranking
* Regional availability

And provides:

* Retry
* Failover
* Circuit breaker
* Invocation logs

---

# 🧩 Build Your Own Tools

```ts
import { defineTool } from "@qveris/sdk";

export default defineTool({
  name: "weather",
  input: { city: "string" },
  output: { temp: "number", desc: "string" },
  async run({ city }) {
    const r = await fetch(`https://api.weather.com?q=${city}`);
    return { temp: r.temp, desc: r.description };
  }
});
```

---

# 🤖 Build an Agent

```ts
import OpenAI from "openai";
import { Qveris } from "@qveris/sdk";

const qv = new Qveris({ apiKey: QVERIS_KEY });

const completion = await client.chat.completions.create({
  model: "gpt-4.1",
  messages: [{ role: "user", content: "Find iPhone prices and summarize." }],
  tools: qv.getToolsForOpenAI()
});
```

---

# 🛒 Marketplace

Publish and monetize tools.
Qveris handles:

* Distribution
* Billing
* Sandbox execution
* Developer payouts

Revenue Share: **10–30%**

---

# 🔐 Enterprise

* VPC / On-prem Deployment
* SSO / SAML / RBAC
* Audit Logs
* Access Policies
* Rate Limits
* SLA 99.9%
* Custom routing rules

---

# 📦 SDKs

| SDK                     | Status            |
| ----------------------- | ----------------- |
| JavaScript / TypeScript | ✅ Available       |
| Python                  | ✅ Available       |
| Go                      | 🚧 In Development |
| Rust                    | 📝 Planned        |

---

# 📈 Pricing

| Plan            | Price          | Monthly Quota   | Features                             |
| --------------- | -------------- | --------------- | ------------------------------------ |
| **Free**        | $0             | 1,000 calls     | Basic tools, low rate limits         |
| **Developer**   | $19/mo         | 50,000 calls    | Standard tools, logs                 |
| **Pro**         | $99/mo         | 1,000,000 calls | Routing optimization, advanced tools |
| **Enterprise**  | $499–20,000/mo | Unlimited       | VPC, RBAC, SLA, compliance           |
| **Marketplace** | Revenue share  | —               | 10–30% developer earnings            |

---

# 🚀 Roadmap

### **Q1**

* SDK JS/Python
* 50 Tools
* Routing (alpha)

### **Q2**

* 200 Tools
* Marketplace v0
* Agent Runtime

### **Q3**

* Billing System
* Global compute regions
* Enterprise features

---

# 🤝 Contributing

We welcome:

* Tool contributions
* Provider integrations
* Bug fixes
* Docs updates
* Feature proposals

---

# 💬 Community

* Discord
* GitHub Discussions
* Twitter/X @QverisAI
* Weekly Dev AMA

---

# ❓ FAQ

### Q: How is Qveris different from LangChain?

LangChain = orchestration framework
Qveris = tool invocations + routing + sandbox + ecosystem

### Q: Does Qveris support GPT tool calling?

Yes — `qv.getToolsForOpenAI()`.

### Q: Can I publish tools?

Yes, via the Marketplace.

---

# ⭐ Star Us

If you like Qveris, please ⭐ the repo —
it helps more developers discover the Tool OS movement!


