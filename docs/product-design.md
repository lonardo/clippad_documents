# Product Design: From Repeated Work to Helpful Context / 产品设计：从重复操作到恰到好处的帮助

OfficeAddin is designed around a simple idea: Office automation should help people finish real work, not make them learn a new, complicated way to work.

OfficeAddin 的设计出发点很简单：Office 自动化应当帮助人完成真实工作，而不是迫使人学习一套复杂的新工作方式。

This page explains the product direction. Specific features and availability can vary by release.

本文介绍产品的设计方向。具体功能和可用范围可能随版本而变化，请以对应版本说明为准。

## Start with the user's work

## 从用户正在做的事开始

Many Office tasks are not single clicks. Preparing a document for delivery, checking a spreadsheet, or cleaning a presentation usually involves several connected steps. A useful assistant should understand that these steps may belong together before it offers help.

许多 Office 任务并不是一次点击就能完成的。准备交付文档、检查表格或整理演示文稿，往往由多个相关步骤组成。有价值的助手应先理解这些步骤可能属于同一项工作，再考虑是否提供帮助。

Our product direction is therefore to move carefully from observable work toward useful context:

因此，产品会谨慎地从可观察的操作逐步走向有用的工作上下文：

```text
confirmed actions
    -> repeatable behaviors
    -> a piece of work in progress
    -> a possible recurring goal
```

```text
已确认的操作
    -> 可复用的行为模式
    -> 正在推进的一项工作
    -> 可能反复出现的工作目标
```

This is not a claim that the product can read a user's mind. It is a way to avoid treating one isolated click as a complete intention.

这并不意味着产品能够“读心”。它的意义在于避免把一次孤立点击误判为完整意图。

## Three surfaces, each useful on its own

## 三个功能面，各自独立有用

OfficeAddin has three complementary ways to help. They can share helpful context, but none requires the user to open another surface first.

OfficeAddin 提供三个互补的帮助入口。它们可以共享有用的上下文，但任何一个都不要求用户先打开另一个入口。

| Surface | What it is for | What users should expect |
|---|---|---|
| Commands and search | Quick access to known, repeatable work | Find and run a familiar command directly |
| Insights | A quiet explanation of an opportunity in the current work | Review it, ignore it, or act locally without being forced elsewhere |
| AI workbench | A place to describe a goal and work through a larger task | Start from the user's request, even when no insight is available |

| 功能面 | 适合解决什么问题 | 用户可以期待什么 |
|---|---|---|
| 指令与搜索 | 快速处理已知、可重复的工作 | 直接找到并运行熟悉的指令 |
| 洞察 | 安静说明当前工作中可能存在的机会 | 可以查看、忽略或在本地完成操作，不会被强制跳转 |
| AI 工作台 | 描述目标并处理较完整的任务 | 从用户的明确请求开始，即使当前没有洞察也可使用 |

For example, a user who knows the command they need should be able to use search immediately. A user who notices an insight should be able to decide locally. A user who has a broader goal should be able to start in the workbench without first creating a suggestion.

例如，已经知道要用什么指令的用户应能立即通过搜索完成操作；看到洞察的用户应能在当前场景自行决定；有更完整目标的用户应能直接打开工作台，而不必先制造一条建议。

## Assistance is optional, not a detour

## 帮助是可选的，不应成为绕路

Connections between commands, insights, and the workbench are intended to reduce repeated explanation. They are not intended to interrupt work, force a page change, or decide a workflow on the user's behalf.

指令、洞察和工作台之间的关联，是为了减少重复描述，不是为了打断工作、强制跳转页面，或替用户决定工作流程。

The product should offer a next step only when it is useful and understandable. The user can always continue with the current task, use a direct command, or decline a suggestion.

产品只应在建议有用且容易理解时提供下一步。用户始终可以继续当前工作、使用直接指令，或忽略建议。

## Evidence before advice

## 先有依据，再给建议

Office work is full of temporary edits: a one-off highlight, an experiment with formatting, or a quick correction. Repetition alone is not enough to conclude that someone wants to automate a process.

Office 工作中充满临时修改：一次性的强调、排版试验或快速修正。仅仅出现重复，并不足以说明用户想把某个过程自动化。

OfficeAddin is designed to be conservative:

OfficeAddin 的设计倾向于保守判断：

- One action should not become a broad conclusion.
- One piece of work should not become a long-term assumption.
- When the evidence is weak, it is better to remain silent or say that more confirmation is needed.
- A suggestion should explain what it is based on and leave room for other interpretations.

- 一次操作不应升级为宽泛结论。
- 一项工作不应升级为长期假设。
- 依据不足时，保持安静或明确说明需要更多确认，比给出武断建议更好。
- 建议应说明依据，并为其他解释留下空间。

This approach favors trust over interruption. A correct “not sure yet” is more valuable than a confident but irrelevant prompt.

这种做法把信任放在打扰之前。一个正确的“暂时无法判断”，比自信却无关的提示更有价值。

## A practical example

## 一个实际例子

Consider a person preparing several documents for delivery. They may standardize headings, tidy body text, review changes, and create a final version. If this is observed as a connected piece of work, the product can eventually offer a coherent way to continue, rather than separately recommending unrelated formatting actions.

设想一位用户正在准备多份待交付文档：统一标题、整理正文、检查修订、形成最终版本。如果这些步骤被理解为相互关联的一项工作，产品未来就可以提供连贯的后续帮助，而不是分别推荐互不相关的格式操作。

Even then, the product should not silently assume that every document follows the same rule. It should show the user what it understands, identify what remains uncertain, and ask for direction when a decision matters.

即使如此，产品也不应擅自认定每份文档都遵循同一规则。它应向用户说明自己的理解，标出仍不确定的部分，并在关键决策处请求用户指示。

## AI supports the work; it does not take ownership

## AI 支持工作，而不替代用户做主

AI can help turn a user's description into a clearer plan, explain unfamiliar options, or identify what information is still missing. It should not silently change documents, present guesses as facts, or bypass the user's choices.

AI 可以帮助把用户描述整理为更清晰的计划、解释不熟悉的选项，或指出仍缺少哪些信息。它不应在没有说明的情况下修改文档、把猜测当作事实，或绕过用户的选择。

For changes that matter, the intended experience is straightforward: understand the scope, review the expected effect, confirm the decision, and then check the result.

对于重要改动，理想体验应当清晰直接：先理解范围，再查看预期影响，确认决定，最后检查结果。

## How we will evolve the experience

## 我们会如何演进体验

The product design is intentionally not tied to one fixed interaction pattern. A card, a small prompt, a workbench summary, or no interruption at all may be appropriate in different situations. We will use user feedback to decide which presentation is useful, understandable, and not disruptive.

产品设计有意不绑定某一种固定交互方式。卡片、小提示、工作台摘要，或完全不打断用户，在不同情境下都可能更合适。我们会根据用户反馈决定何种呈现真正有用、易理解且不过度打扰。

The direction remains stable: help with real Office work, preserve user control, make uncertainty visible, and turn trusted repeated work into reusable help over time.

方向保持不变：围绕真实 Office 工作提供帮助，保留用户控制权，让不确定性可见，并逐步把可信的重复工作沉淀为可复用的帮助。
