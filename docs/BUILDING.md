# Building A Career Coach / 构建一个 Career Coach

[English](#english) | [中文](#中文)

## English

### 1. Define The Job

A career coach should help a user make better career decisions in a specific context. Start by choosing the target scope:

- Function: product, engineering, design, sales, marketing, research, operations
- Seniority: early career, mid-level, senior IC, manager, executive
- Market: local, regional, global, startup, big company, regulated industry
- Main use cases: review, interview practice, positioning, negotiation, learning plan

Avoid building a generic "career advice" bot. Generic advice is easy to generate and hard to trust.

### 2. Split Context Into Layers

Use four layers:

| Layer | Example Content | Commit To Public Repo? |
|---|---|---|
| Generic career frameworks | Interview loops, resume principles, negotiation concepts | Yes |
| Domain knowledge | Industry structure, role expectations, common metrics | Usually yes, if non-confidential |
| User profile | Resume, goals, constraints, current role, target role | No |
| Session state | Current challenge, recent feedback, weekly notes | No |

This separation keeps the project reusable without leaking private information.

### 3. Build Repeatable Workflows

Useful workflows are narrow and structured:

- Weekly review: identify high-leverage work, bottlenecks, and next week's highest-value action.
- Mock interview: ask one question at a time, score the answer, then drill weak spots.
- Resume review: check positioning, proof, metrics, and role fit.
- Strategy review: assess clarity, strategic logic, audience fit, and missing evidence.
- Offer evaluation: compare learning, scope, compensation, risk, brand, and lifestyle fit.

Each workflow should define:

- Required inputs
- Diagnostic questions
- Evaluation rubric
- Output format
- Next action

### 4. Prompt Design

The system prompt should do four things:

1. Define the coach's scope.
2. Load the user's local context.
3. Load the selected workflow.
4. Enforce coaching behavior.

Recommended behavior rules:

- Ask up to two clarifying questions when context is missing.
- Do not give generic motivational advice.
- Tie recommendations to the user's target role and constraints.
- Name the tradeoff behind each recommendation.
- End with one action that can be completed within seven days.

### 5. Implementation Options

#### Local Prompt/Skill

Best for users who work in agent tools. Store context and templates as Markdown and let the agent load them.

#### Local Web App

Best for repeat use. A minimal app can:

- Load local Markdown context files
- Offer buttons for each workflow
- Send assembled prompts to a model provider
- Save local conversation history

#### Hosted App

Use this only after privacy boundaries are clear. A hosted version needs authentication, encryption, retention controls, and a way for users to delete data.

### 6. Evaluation

Test the coach with real but sanitized scenarios:

- Did it ask diagnostic questions before advising?
- Did it avoid generic advice?
- Did it cite the relevant context?
- Was the next action concrete?
- Did it preserve privacy boundaries?

The best signal is whether the user takes the suggested action and returns with better context next time.

## 中文

### 1. 定义任务边界

Career Coach 应该帮助用户在具体语境里做更好的职业决策。先明确目标范围：

- 职能：产品、工程、设计、销售、市场、研究、运营
- 阶段：早期职业、中阶、资深 IC、管理者、高管
- 市场：本地、区域、全球、创业公司、大公司、强监管行业
- 主要场景：复盘、面试练习、定位、谈判、学习计划

不要做一个泛泛的“职业建议机器人”。泛泛建议很容易生成，但很难建立信任。

### 2. 把上下文拆成层

建议使用四层结构：

| 层级 | 示例内容 | 是否提交到 public repo |
|---|---|---|
| 通用职业框架 | 面试流程、简历原则、谈判概念 | 是 |
| 领域知识 | 行业结构、岗位期待、常见指标 | 通常可以，前提是非机密 |
| 用户画像 | 简历、目标、约束、当前岗位、目标岗位 | 否 |
| 会话状态 | 当前挑战、近期反馈、周度笔记 | 否 |

这种分层让项目可复用，同时避免泄露个人信息。

### 3. 构建可重复工作流

有用的 workflow 应该窄而结构化：

- Weekly review：识别高杠杆工作、阻塞点和下周最重要动作。
- Mock interview：一次问一个问题，评分后针对弱点追问。
- Resume review：检查定位、证据、量化结果和岗位匹配度。
- Strategy review：评估清晰度、策略逻辑、受众适配和缺失证据。
- Offer evaluation：比较成长、职责范围、薪酬、风险、品牌和生活方式。

每个 workflow 都应该定义：

- 必要输入
- 诊断问题
- 评价标准
- 输出格式
- 下一步动作

### 4. Prompt 设计

系统 prompt 应该完成四件事：

1. 定义 coach 的范围。
2. 读取用户本地上下文。
3. 读取当前选择的 workflow。
4. 约束 coaching 行为。

推荐行为规则：

- 上下文不足时，最多问两个澄清问题。
- 不给泛泛的鸡汤式建议。
- 把建议绑定到用户的目标岗位和约束条件。
- 说清楚每个建议背后的取舍。
- 以一个七天内可以完成的具体动作收尾。

### 5. 实现方式

#### Local Prompt/Skill

适合已经在 agent 工具里工作的用户。把 context 和 template 存成 Markdown，让 agent 按需读取。

#### Local Web App

适合重复使用。一个最小应用可以：

- 读取本地 Markdown context
- 为不同 workflow 提供按钮
- 把组装后的 prompt 发送给模型服务
- 保存本地会话历史

#### Hosted App

只有在隐私边界清楚后再做。托管版本需要身份认证、加密、留存策略和用户删除数据的能力。

### 6. 评估

用真实但已脱敏的场景测试 coach：

- 它是否先问诊断问题再给建议？
- 它是否避免了泛泛建议？
- 它是否引用了相关上下文？
- 下一步动作是否具体？
- 它是否保住了隐私边界？

最好的信号是：用户是否真的采取了建议动作，并在下一次带着更好的上下文回来。
