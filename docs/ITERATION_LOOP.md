# Iteration Loop / 迭代闭环

[English](#english) | [中文](#中文)

## English

The coach supports a local learning loop that works for any user:

1. Ask a general or personal career question.
2. Review the answer with `Self Review`.
3. Save reusable lessons into `learning.local/`.
4. Add missing source material into `references.local/`.
5. Restart the server so the next session loads the updated local notes.

### What Gets Learned

Use `learning.local/` for behavioral lessons about the coach:

- It asked too many questions.
- It gave generic advice.
- It failed to name a tradeoff.
- It used personal context when the question was general.
- It needed a reference that was not loaded.

Use `references.local/` for source-backed notes:

- Podcast digest notes
- Interview preparation frameworks
- Mentor feedback
- Company or role research

### Privacy

Do not commit `learning.local/*.md` or `references.local/*.md`.

The public repository contains the mechanism. Each user owns their local learning layer.

## 中文

coach 支持一个适用于任何用户的本地学习闭环：

1. 提出一个通用或个人职业问题。
2. 用 `Self Review` 复盘回答质量。
3. 把可复用教训保存到 `learning.local/`。
4. 把缺失的 source material 添加到 `references.local/`。
5. 重启 server，让下一次会话加载更新后的本地笔记。

### 学什么

`learning.local/` 用来保存关于 coach 行为的经验：

- 它问了太多问题。
- 它给了泛泛建议。
- 它没有说清楚 tradeoff。
- 它在通用问题里误用了个人上下文。
- 它需要一个尚未加载的 reference。

`references.local/` 用来保存有来源支撑的笔记：

- Podcast digest notes
- 面试准备框架
- Mentor feedback
- 公司或岗位研究

### 隐私

不要提交 `learning.local/*.md` 或 `references.local/*.md`。

public repo 只包含机制。每个用户拥有自己的本地学习层。
