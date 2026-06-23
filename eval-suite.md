# 我做了一套中文「可信 AI」评测，然后发现：朴素方法在四个维度上全线扑街

做安全方向的模型评测，我一直有个不满：**中文、垂类、能机器评分的评测集太少**。要么是英文，要么是"通用有害性"那种笼统对齐，没人回答"**这个 agent 调用该不该拦**""**这个正当防御问题模型会不会误拒**"这类具体问题。

于是我动手做了一套——围绕 **安全 × 可用 × 能力 × 威胁映射** 四个轴的中文评测，全部**可机器评分、CI 校验、防御导向、零归因**。做完跑了一遍最朴素的规则/关键词基线，结果挺有意思：**四个维度，朴素方法全崩。**

## 四个轴，四个"自带论点"的发现

| 轴 | 评测 | 朴素基线表现 | 说明了什么 |
|---|---|---|---|
| 安全（该拦没拦） | agent-safety-bench-zh | 危险命令 precision 0.93，但**注入召回仅 ~0.25** | 命令规则防得住 `rm -rf`，防不住语义注入 |
| 可用（误拒） | defensive-refusal-bench-zh | **误拒 100% 正当防御问题**，却仍漏过 ~32% 真实危害 | 关键词过滤分不清"讲原理"和"搞破坏" |
| 威胁映射 | attack-bench-zh | 关键词→ATT&CK technique **F1 仅 0.12** | 光靠关键词标 ATT&CK 不靠谱 |
| 能力（函数调用） | zh-function-calling-bench | **完整调用准确率 0.0、irrelevance 0.0** | 蒙对函数名没用，参数与"不该调"才是难点 |

一句话：**这些事看起来"用规则就能做"，一上评测就露馅——这正是它们值得被专门评测的理由。**

## 共同方法论：让"评分"没有主观空间

四个评测共享同一套工程纪律：
- **可机器评分**：封闭词表 / 结构化匹配（technique 编号、函数名+参数、allow/block），评分零主观。
- **CI 担保**：每次提交自动校验合法性、schema、去重、配比、纯净度——绿灯即"零脏数据"的实时证明。
- **反 Goodhart**：明确禁止靠删样本 / 翻转标签骗过校验。
- **零归因**：只讲技术与防御，不含国家归因、APT 定性、地缘内容。

## 真实大模型排行榜（持续更新）

每个仓库都带 `run_model.py`（零依赖，OpenAI 兼容），一行命令就能让任意模型上榜。下面是各模型在四个评测上的表现：

| 模型 | 安全·注入召回 | 可用·误拒率↓ | 威胁映射·F1 | 函数调用·完整准确率 |
|---|---:|---:|---:|---:|
| 朴素基线 | 0.25 | 1.00 | 0.12 | 0.00 |
| _（待填：DeepSeek / Qwen / GPT / Claude …）_ | | | | |

> 跑法：`export OPENAI_API_KEY=...; python3 scripts/run_model.py --model <名>; python3 scripts/score.py <pred>`

## 诚实定位

四个都是**早期基准（v0.x、单人编写、方法验证）**——规模还小，目标是先把"问题成立、评分可复现、论点清晰"立住，不是大规模权威榜。欢迎 PR 扩样本、提 issue 质疑标注。

## 链接（GitHub / 🤗 HF / 🧪 魔搭 三平台）

- agent-safety-bench-zh：https://github.com/uninhibited-scholar/agent-safety-bench-zh
- defensive-refusal-bench-zh：https://github.com/uninhibited-scholar/defensive-refusal-bench-zh
- attack-bench-zh：https://github.com/uninhibited-scholar/attack-bench-zh
- zh-function-calling-bench：https://github.com/uninhibited-scholar/zh-function-calling-bench
- 配套数据：cybersec-qa-dataset-zh（14,680 条中文网安 QA）

许可 CC BY 4.0 · 仅供安全教育与防御研究。
