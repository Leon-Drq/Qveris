<p align="right">
  <a href="README.md">🇺🇸 English</a> | <b>🇨🇳 简体中文</b>
</p>

<p align="center">
  <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA5IAAAOSCAIAAACJE3hFAAEAAElEQVR4nOz9R7M...UChrQUFBQUFBQUFBe8BCm0tKCgoKCgoKCh4D1Boa0FBQUFBQUFBwXuAQlsLCgoK" width="160" />
</p>

<p align="center">
  <b>Qveris —— 面向 AI Agents 的工具操作系统（Tool OS）</b><br/>
  <sub>让你的大模型，用一个接口调用全世界的工具。</sub>
</p>

---

# 📘 目录

- [✨ 简介](#-简介)
- [💡 为什么需要 Qveris？](#-为什么需要-qveris)
- [🆘 Qveris 能解决哪些痛点？](#-qveris-能解决哪些痛点)
- [🔧 核心特性](#-核心特性)
- [🏗 架构图](#-架构图)
- [⚡ 快速开始](#-快速开始)
- [🧰 内置工具（部分展示）](#-内置工具部分展示)
- [⚔ 竞品对比](#-竞品对比)
- [🔌 工具协议标准（Tool Schema）](#-工具协议标准tool-schema)
- [🧠 工具路由引擎（Routing Engine）](#-工具路由引擎routing-engine)
- [🛠 自定义工具](#-自定义工具)
- [🤖 构建一个智能 Agent](#-构建一个智能-agent)
- [🛒 工具市场（Marketplace）](#-工具市场marketplace)
- [🔐 企业版本特性](#-企业版本特性)
- [📦 SDK 支持](#-sdk-支持)
- [📈 定价（Pricing）](#-定价pricing)
- [🚀 产品路线图](#-产品路线图)
- [🤝 如何贡献](#-如何贡献)
- [💬 社区](#-社区)
- [❓ 常见问题 FAQ](#-常见问题-faq)
- [⭐ 支持我们](#-支持我们)

---

# ✨ 简介

**Qveris 是一个面向 AI 时代的工具操作系统（Tool OS）**。

它将全世界的第三方工具、API、操作指令、数据服务标准化，让大模型（LLM）可以通过 **一个统一接口** 调用任意工具。

包括：

- 搜索（Search）
- OCR
- PDF 解析
- 信息抽取
- HTTP 通用请求
- 天气 / 金融 / 新闻 / 数据服务
- 邮件、Slack、自动化操作
- 企业内部 API 工具
- 任意自定义工具

> **Qveris = Kubernetes + Homebrew + Zapier（但用于 AI 工具调用）。**

---

# 💡 为什么需要 Qveris？

大模型要真正“行动起来”，必须依赖工具。  
但当前工具生态极度混乱：

- API 风格不同  
- JSON 格式不一致  
- 调用方式不同  
- 权限、安全机制不同  
- 无日志、无审计、无可靠性  
- 无统一协议  
- 无可复用生态  

Qveris 的使命是：

> **让大模型像人一样自然、安全、标准化地调用工具。**

---

# 🆘 Qveris 能解决哪些痛点？

### ❗ 当前大模型调用第三方工具存在巨大痛点：

| 问题 | 描述 |
|------|------|
| ❌ **工具生态破碎** | OpenAI、Kimi、Zhipu、Llama 工具互不兼容，无法互通 |
| ❌ **安全无法保证** | 工具访问数据库、API、文件系统，风险巨大 |
| ❌ **开发成本巨大** | 每接一个工具都要单独写认证、限流、重试、日志 |
| ❌ **行为不可控** | LLM 行为不可预测，难以监控执行日志与回滚 |

---

### ✅ Qveris 统一解决：

| 方案 | 描述 |
|------|------|
| ⭐ **统一标准** | 所有工具封装成可控、可审计的“Q-Tool” |
| ⭐ **安全沙箱** | 工具在隔离环境中执行 |
| ⭐ **统一协议** | LLM 自然调用、组合、编排工具 |
| ⭐ **可观测性** | 完整日志、权限、行为追踪 |

---

# 🔧 核心特性

- ✔ **统一工具 Schema**（输入/输出一致）
- ✔ **200+ 内置工具**
- ✔ **工具路由（最优 Provider 自动选择）**
- ✔ **安全沙箱**
- ✔ **工具市场（Marketplace）**
- ✔ **与所有主流 Agent 框架兼容**
- ✔ **企业级权限 / 审计 / 访问控制**

---

# 🧰 内置工具（部分展示）

<p align="center">
<img src="https://dummyimage.com/1000x300/1a1a1a/ffffff&text=Built-in+Tools" width="100%" />
</p>

工具类别包括：

- 搜索（Google、Bing、Arxiv...）
- OCR（Vision API、PaddleOCR、Tesseract）
- PDF 文档抽取
- 信息抽取（结构化 JSON）
- HTTP 通用请求
- 天气 / 股票 / 新闻 / 加密 / 数据服务
- 自动化（邮件、Slack、Webhook）
- 自定义企业工具

---

# ⚔ 竞品对比

| 产品 | Qveris | OpenAI Plugins | LangChain Tools | Kimi Tools |
|------|--------|----------------|----------------|------------|
| **开放性** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐ |
| **安全沙箱** | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐ | ⭐⭐ |
| **统一协议** | ⭐⭐⭐⭐⭐ | ⭐ | ❌ | ❌ |
| **工具生态** | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐ | ⭐ |
| **适配大模型** | ⭐⭐⭐⭐⭐ | ⭐ | ⭐⭐⭐⭐ | ❌ |

> **Qveris 是当前最完整、最通用的工具调用基础设施。**

---

# 🏗 架构图

