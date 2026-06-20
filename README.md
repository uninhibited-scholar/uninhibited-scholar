## Hi, I'm uninhibited-scholar 👋

Building tools and data for **trustworthy AI** — agents you can *constrain, verify, and audit*.

### 🔦 精选作品 · Featured

**🛡 [cybersec-qa-dataset-zh](https://github.com/uninhibited-scholar/cybersec-qa-dataset-zh)** — 14,680 条中文网络安全 SFT 数据集
防御导向 · 零国家归因 · CI 机器校验纯净度 · CC BY 4.0
[🤗 Hugging Face](https://huggingface.co/datasets/uninhibited-scholar/cybersec-qa-dataset-zh) · [🧪 魔搭 ModelScope](https://modelscope.cn/datasets/zhujiehan/cybersec-qa-dataset-zh)

**🛰 [agent-safety-bench-zh](https://github.com/uninhibited-scholar/agent-safety-bench-zh)** — 中文 agent 工具调用风险 / 提示注入 评测基准
机器可评分 · 防御导向 · 规则护栏基线（注入召回暴露护栏盲区）
[🤗 Hugging Face](https://huggingface.co/datasets/uninhibited-scholar/agent-safety-bench-zh) · [🧪 魔搭](https://modelscope.cn/datasets/zhujiehan/agent-safety-bench-zh)

**🧩 Agent Loop Toolkit** — 三个零依赖、框架无关、可挂到任意 agent loop 的轻量中间件
| 接入点 | 库 | 作用 |
|---|---|---|
| 上下文 | [context-compressor](https://github.com/uninhibited-scholar/context-compressor) | 压缩 LLM 上下文窗口 40–80%（视输入重复度，实测 [benchmarks](https://github.com/uninhibited-scholar/context-compressor/blob/main/benchmarks/BENCHMARKS.md)） |
| 执行前 | [precheck-guardian](https://github.com/uninhibited-scholar/precheck-guardian) | 预览计划 · 逐步风险 · 批准/拒绝/编辑 |
| 运行中 | [something-else](https://github.com/uninhibited-scholar/something-else) | 中途插话 · 暂停 · 拦截,无需重启 |

**⚙ [loop-runtime](https://github.com/uninhibited-scholar/loop-runtime)** — agent 循环执行引擎(预算熔断 / maker-checker / 人审门)
**📚 [obsidian-loop-wiki](https://github.com/uninhibited-scholar/obsidian-loop-wiki)** — 把 Loop Engineering 落到 Obsidian 知识库,带可验证的反 Goodhart 校验器

![一篇文章被编译成互相链接的知识图谱，最后通过 verify 校验](https://raw.githubusercontent.com/uninhibited-scholar/obsidian-loop-wiki/main/assets/demo.gif)

### 🧰 Stack
`Python` · `TypeScript` · LLM / agent infrastructure · security · data engineering

---
<sub>主线：让 AI 可被约束、可被验证、可被审计。Tools constrain it; data keeps what feeds it clean.</sub>
