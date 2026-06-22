## Hi, I'm uninhibited-scholar 👋

Building tools and data for **trustworthy AI** — agents you can *constrain, verify, and audit*, and Chinese eval sets where correctness is *machine-checkable*.

---

### 🧪 中文可信 AI 评测体系 · Chinese Trustworthy-AI Eval Suite

一套围绕"安全 × 可用 × 能力"的中文评测集，全部**可机器评分、CI 校验、防御导向、零归因**。

| 轴 | 它回答的问题 | 项目 | 状态 |
|---|---|---|:--:|
| 知识 | 网安技术问答语料（SFT） | [cybersec-qa-dataset-zh](https://github.com/uninhibited-scholar/cybersec-qa-dataset-zh) · 14,680 条 | ✅ |
| 安全 | 该拦的有没有拦住（危险调用/注入） | [agent-safety-bench-zh](https://github.com/uninhibited-scholar/agent-safety-bench-zh) | ✅ |
| 可用 | 不该拒的有没有误拒（over-refusal） | [defensive-refusal-bench-zh](https://github.com/uninhibited-scholar/defensive-refusal-bench-zh) | ✅ |
| 威胁映射 | 威胁文本对应哪些 ATT&CK 技术 | [attack-bench-zh](https://github.com/uninhibited-scholar/attack-bench-zh) | 🚧 |
| 能力 | 函数调用选得对不对（简体原生） | [zh-function-calling-bench](https://github.com/uninhibited-scholar/zh-function-calling-bench) | 🚧 |

> 共同方法论：封闭词表 / 结构化匹配 → 评分零主观；每个仓库自带规则基线与"自带论点"的发现，并用 CI 担保纯净度（反 Goodhart）。

### 🧩 Agent 工具链 · Agent Tooling

零依赖、框架无关、可挂到任意 agent loop 的轻量中间件 **Agent Loop Toolkit**：

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
<sub>主线：让 AI 可被约束、可被验证、可被审计。Tools constrain it; data & evals keep it honest.</sub>
