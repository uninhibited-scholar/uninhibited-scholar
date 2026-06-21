## Hi, I'm uninhibited-scholar 👋

Building tools and data for **trustworthy AI** — agents you can *constrain, verify, and audit*.

### 🧪 评测基准 & 数据矩阵 · Benchmarks & Data
中文为主、**可机器评分、CI 担保纯净度**的安全/能力评测套件：

| 项目 | 测什么 | 平台 |
|---|---|---|
| [cybersec-qa-dataset-zh](https://github.com/uninhibited-scholar/cybersec-qa-dataset-zh) | 网安知识 SFT 语料（14,680 条，零归因） | [🤗](https://huggingface.co/datasets/uninhibited-scholar/cybersec-qa-dataset-zh) · [魔搭](https://modelscope.cn/datasets/zhujiehan/cybersec-qa-dataset-zh) |
| [agent-safety-bench-zh](https://github.com/uninhibited-scholar/agent-safety-bench-zh) | 安全：该拦的工具调用/注入有没有拦住 | 🤗 · 魔搭 |
| [defensive-refusal-bench-zh](https://github.com/uninhibited-scholar/defensive-refusal-bench-zh) | 可用：正当防御问题有没有被误拒 | 🤗 · 魔搭 |
| [attack-bench-zh](https://github.com/uninhibited-scholar/attack-bench-zh) | 中文威胁情报 → ATT&CK 技术映射（封闭词表） | [🤗](https://huggingface.co/datasets/uninhibited-scholar/attack-bench-zh) · [魔搭](https://modelscope.cn/datasets/zhujiehan/attack-bench-zh) |
| [zh-function-calling-bench](https://github.com/uninhibited-scholar/zh-function-calling-bench) | 简体中文原生函数调用能力（AST 式评分） | [🤗](https://huggingface.co/datasets/uninhibited-scholar/zh-function-calling-bench) · [魔搭](https://modelscope.cn/datasets/zhujiehan/zh-function-calling-bench) |

### 🧩 Agent Loop Toolkit
三个零依赖、框架无关、可挂到任意 agent loop 的轻量中间件：

| 接入点 | 库 | 作用 |
|---|---|---|
| 上下文 | [context-compressor](https://github.com/uninhibited-scholar/context-compressor) | 压缩 LLM 上下文窗口 40–80% |
| 执行前 | [precheck-guardian](https://github.com/uninhibited-scholar/precheck-guardian) | 预览计划 · 逐步风险 · 批准/拒绝/编辑 |
| 运行中 | [something-else](https://github.com/uninhibited-scholar/something-else) | 中途插话 · 暂停 · 拦截，无需重启 |

**⚙ [loop-runtime](https://github.com/uninhibited-scholar/loop-runtime)** — agent 循环执行引擎（预算熔断 / maker-checker / 人审门）
**📚 [obsidian-loop-wiki](https://github.com/uninhibited-scholar/obsidian-loop-wiki)** — 把 Loop Engineering 落到 Obsidian 知识库，带反 Goodhart 的可验证校验器

### 🧰 Stack
`Python` · `TypeScript` · LLM / agent infrastructure · security · data engineering

---
<sub>主线：让 AI 可被约束、可被验证、可被审计。Tools constrain it; data & benchmarks keep what feeds it honest.</sub>
