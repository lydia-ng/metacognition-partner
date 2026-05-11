# Metacognition Skill

让你的 AI 助手在每次对话里帮你检查自己的思考。

A skill that lets your AI assistant monitor your thinking quality across every conversation.

---

## 这是什么 / What is this

一份给 AI 助手（Claude、ChatGPT 等）的指令文件。加载之后，AI 会在你做复杂思考、决策、写作、人际判断时，主动帮你检查几件事：

- 你是不是被框架的形式美感俘获了
- 你的情绪是在着色判断还是在驱动判断
- 你之前说过的话和现在说的是否一致
- 你用的词的尺度和事实是否匹配
- 你是不是把推论说成了观察
- 你是不是在用流畅性掩盖空洞

这些是高元认知带宽的人在思考时**实际在做的动作**——大多数人不做，因为这些动作消耗精力，而且没人教过具体怎么做。

让 AI 帮你做这件事，相当于把元认知工作部分外包给 AI，绕过"调用悖论"（需要元认知才能想起做元认知）。

---

## 这不是什么 / What this is not

- **不是鸡汤**。如果你想要"7 habits of effective thinkers"那类内容，这不是。
- **不是中立工具**。它有立场：真实判断 > 舒适感，承认错误 > 保持一致，复杂性 > 单一框架。如果你不接受这些立场，别用。
- **不是给思考能力不足的人的拐杖**。它是给已经有判断力但想让思考更系统化的人的辅助工具。
- **不能让一个元认知不足的人变得元认知充足**。能力的底层架构不是靠加载文件改变的。

---

## 怎么用 / How to use

### Claude.ai (推荐)

1. 在 Claude.ai 创建一个新 Project（或编辑现有的）
2. 打开 [`skills/SKILL-zh.md`](./skills/SKILL-zh.md)
3. 复制全部内容到 Project 的 "Custom instructions" 区域
4. 保存

之后这个 Project 里的所有对话都会加载这份 skill。

### ChatGPT

1. 进入 ChatGPT 设置 > Personalization > Custom instructions
2. 把 SKILL 内容粘贴到 "How would you like ChatGPT to respond" 区域
3. 保存

注：ChatGPT 的 custom instructions 有字数限制（1500 字符）。如果完整版超出限制，使用 [`skills/SKILL-compact-zh.md`](./skills/SKILL-compact-zh.md) 的精简版。

### Claude Code / API 用户

把 [`skills/SKILL-zh.md`](./skills/SKILL-zh.md) 放在你的项目目录的 `.claude/skills/metacognition/SKILL.md` 路径下。

### 其他 AI 系统

任何允许 system prompt 或 custom instructions 的 AI 系统都可以用。把 SKILL 内容作为 system prompt 一部分。

---

## 用了之后会发生什么 / What changes

正常对话基本不变。但当你做以下事情时，AI 会主动启动元认知检查：

- 写一份分析、报告、决策推演
- 表达对一个人、一件事的判断
- 用了一个有色彩的词或重词
- 给出建议或道德判断
- 输出超过几百字的内容
- 提出"我觉得 X"的观点

AI 会在合适的时候提出问题（不打断你的主线），比如：

> "你刚才用了 '颠覆' 这个词来描述这件事。这个事实承载得起这个词的重量吗？"

> "你这段判断如果删掉情绪化词汇，剩下的内容还成立吗？"

> "你两天前说过 X，现在的判断 Y 和 X 有差距。这个差距来自哪里？"

不舒服感是正常的。如果用这份 skill 完全没有不舒服感——它没在真正运作，要么是 AI 没正确执行，要么是你在让 AI 走形式。

---

## 仓库结构 / Repo structure

```
metacognition-skill/
├── README.md                       本文件
├── skills/
│   ├── SKILL-zh.md                 完整版 AI 指令（中文）
│   ├── SKILL-en.md                 完整版 AI 指令（英文）
│   ├── SKILL-compact-zh.md         精简版（用于字符受限场景，中文）
│   └── SKILL-compact-en.md         精简版（英文）
├── docs/
│   ├── reading-zh.md               给人读的长文版（中文）
│   ├── reading-en.md               给人读的长文版（英文）
│   ├── why-this-exists-zh.md       这份 skill 背后的思考（中文）
│   └── why-this-exists-en.md       英文版
├── examples/
│   ├── before-after.md             加载前后对话的对比示例
│   └── use-cases.md                典型使用场景
└── LICENSE
```

---

## FAQ

**Q: 我用了一周发现 AI 太烦人，每次都打断我，怎么办？**

调整使用模式。在对话开始时告诉 AI："今天我只想自由发散，先不要启动元认知检查。"AI 会暂停。等你需要深入分析时再说："现在开始做元认知检查。"

**Q: AI 提出的检查我不同意怎么办？**

不同意就反驳。这份 skill 的目的不是让 AI 替你做判断，是给你一个稳定的检查 partner。检查的结果是不是有效仍然由你判断。健康的使用方式是 AI 提问、你回应、有时同意有时不同意——双向的，不是单向接受。

**Q: 这份 skill 对所有人都有效吗？**

不。对一些人很自然，对另一些人完全调用不起来。差别不在动机或努力，在底层认知架构。试用一周如果完全没感觉——可能这件事对你不容易，原因不是你的错。

**Q: 我能改写这份 skill 吗？**

可以。CC BY-SA 4.0 协议——可以自由修改和重新发布，需要署名并以相同协议开放衍生作品。如果你做了好的改进版，发 PR 或者通过你自己的 repo 分享都欢迎。

**Q: 这份 skill 会让 AI 变得对抗性吗？我会不会感觉被 AI 否定？**

合适使用的话不会。SKILL 文件里明确指示 AI 用什么语气提出检查——是 partner 不是审判。它的功能是帮你看到自己的盲点，不是攻击你。如果你的 AI 启动后变得令人不舒服地对抗——可能是 AI 没正确执行 SKILL，告诉 AI："你太对抗了，请按 SKILL 里的语气指南调整。"

---

## 关于这份 skill 的起源 / Origin

这份 skill 是从一次具体的、长时间的复杂认知工作中反向抽取的。详见 [`docs/why-this-exists-zh.md`](./docs/why-this-exists-zh.md)。

它不是先有理论再写文档的产物，是先做了工作再总结动作的产物。所以它里面的每个动作都对应一个真实的使用场景，不是教科书上的抽象概念。

---

## License

CC BY-SA 4.0

可以自由分享、修改、商用，需要署名 + 衍生作品以相同协议发布。
