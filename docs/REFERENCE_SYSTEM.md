# Reference System / 知识引用系统

[English](#english) | [中文](#中文)

## English

The Career Coach has three knowledge layers:

1. Public generic references: `references/*.md`
2. Private or licensed local notes: `references.local/*.md`
3. Personal user context: `context/*.local.md`

This lets the coach answer cross-person general questions while still supporting personalized coaching when local context exists.

### Why This Matters

Without a reference layer, the coach is only a prompt wrapper around a user profile. With a reference layer, it can answer questions like:

- How should I prepare for a product interview?
- How do I decide whether to accept an offer?
- How do I build influence without formal authority?
- How do I turn project work into promotion evidence?

These questions can be answered generally first, then personalized with a user profile.

### Lenny Podcast Notes

Lenny's Podcast can be used as a reference source, but the public repo should not contain full transcripts, full episode notes, or long copyrighted summaries.

Recommended approach:

1. Maintain public source metadata and short, transformative principles in `references/`.
2. Keep detailed personal notes or licensed summaries in `references.local/`.
3. Organize notes by theme, not only by episode.
4. Require source URLs for every note.
5. Make the coach say when a claim is unsupported by the loaded notes.

### Suggested Lenny Digest Format

```markdown
# Lenny Digest Local

## Product Judgment

### Source: <episode title and URL>
- Principle:
- Use when:
- Watch out:

## Career Growth

### Source: <episode title and URL>
- Principle:
- Use when:
- Watch out:
```

### Cross-Individual Question Handling

The coach should classify every request:

| Request type | Behavior |
|---|---|
| General career question | Answer from references and domain knowledge |
| Role-specific but not personal | Ask for role/seniority only if missing |
| Personal decision | Ask for up to two diagnostic facts |
| Confidential work issue | Use local profile only; avoid committing details |

### Completeness

The generic public repo should provide the mechanism and starter references. A complete reference library requires one of:

- User-authored notes
- Licensed summaries
- Public source metadata plus short original principles
- A private local knowledge base

The code intentionally supports this through `references.local/`.

## 中文

Career Coach 有三层知识：

1. 公开通用 reference：`references/*.md`
2. 私有或授权的本地笔记：`references.local/*.md`
3. 用户个人上下文：`context/*.local.md`

这样 coach 可以先回答跨个体的通用职业问题；如果本地存在用户画像，再进一步个性化。

### 为什么重要

如果没有 reference 层，coach 只是套在用户画像上的 prompt wrapper。有了 reference 层，它可以回答：

- 我应该如何准备产品面试？
- 我应该如何判断是否接受一个 offer？
- 没有正式 authority 时，如何建立影响力？
- 如何把项目工作转化成晋升证据？

这些问题可以先通用回答，再结合用户画像个性化。

### Lenny Podcast 笔记

Lenny's Podcast 可以作为 reference 来源，但 public repo 不应该包含完整 transcript、完整 episode notes 或长篇受版权保护的总结。

推荐做法：

1. 在 `references/` 中维护公开 source metadata 和短小、转化后的原则。
2. 把详细个人笔记或授权 summary 放在 `references.local/`。
3. 按主题组织笔记，而不只是按 episode。
4. 每条笔记都要求 source URL。
5. 当 claim 没有被已加载笔记支持时，coach 需要明确说明。

### 建议的 Lenny Digest 格式

```markdown
# Lenny Digest Local

## Product Judgment

### Source: <episode title and URL>
- Principle:
- Use when:
- Watch out:

## Career Growth

### Source: <episode title and URL>
- Principle:
- Use when:
- Watch out:
```

### 跨个体问题处理

coach 应该对每个请求分类：

| 请求类型 | 行为 |
|---|---|
| 通用职业问题 | 从 references 和 domain knowledge 回答 |
| 岗位相关但非个人问题 | 如果缺少角色/资历信息，只补问这些 |
| 个人决策 | 最多询问两个诊断事实 |
| 机密工作问题 | 只使用本地画像；避免提交细节 |

### 完整性

通用 public repo 应该提供机制和 starter references。完整 reference library 需要以下之一：

- 用户自写笔记
- 授权 summary
- 公开 source metadata + 简短原创原则
- 私有本地知识库

代码通过 `references.local/` 支持这种扩展方式。
