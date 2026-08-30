# koda-youtube-scripting

**YouTube 口播逐字稿写作 Agent Skill：因果链输入 + 非虚构故事框架 + 罗振宇叙事引擎 + 情绪设计**

An agent skill for writing 8-15 minute YouTube talking-head scripts (Chinese). Core idea: the creator supplies the causal chain (the "why"); the AI does storyization only (the "how") — scenes, conflict, emotion. Opinions are never outsourced.

## 为什么做这个 skill

用 AI 写口播稿最常见的失败：稿子很顺，但观点是 AI 的，不是你的。改十版都不满意，因为根子上写的是别人的稿。

这个 skill 把分工定死：**创作者管"为什么"（观点与因果），AI 管"怎么讲"（故事、冲突、情绪）**：

1. **因果链是创作者的输入件（硬规则）**——创作者先给这期内容的因果链（因为…所以…但是…因此…），AI 按链做故事化施工，不许改链、不许自造链
2. **事实先行**——写作只许用材料包里登记过的事实，每个数字有溯源表，没有来源就不进稿
3. **范本先行**——动笔前按题材通读一篇同题材叙事范本找语感，范本永远优先于模板表格
4. **故事就是论证**——叙事层内置从罗辑思维 1261 期公开节目逐字稿蒸馏的"递进否定"故事引擎：立错误答案 → 完整故事拆掉 → 论点后置短句砸
5. **情绪是骨架不是装修**——故事线阶段就排情绪温度（暖→稳→掀→沉→清→轻收），不留到润色

## 流水线

```
step01 选题确认（观众判定 / 利益落点 / 素材盘点）
   ↓
step02 事实与材料（素材清单 / 数字溯源表 / 缺口清单）
   ↓
step03 故事线设计 ★创作者给因果链，AI 只故事化★
       （Scene 选点 / 冲突 / 情绪温度 / 删层测试 / 3 组标题封面）
   ↓
step04 写作（范本通读 → 结构标注版草稿，时间戳与字数自洽）
   ↓
step05 自检交付（禁词机检 / 流失点三维 / 30 秒测试 / 因果链对账 / 叙事评分卡）
```

## 文件结构

```
SKILL.md                        入口：流程总纲 + 两条铁律 + 执行规范
workflow/
  step01-topic.md               选题确认
  step02-materials.md           事实与材料
  step03-structure.md           故事线设计（含判断挖掘问题库附录）
  step04-draft.md               写稿规则
  step05-check.md               检查链
reference/
  standard-structure.md         六块骨架 + 九硬规则 + 禁区（观点型）
  story-framework.md            非虚构故事框架十一条（个人叙事型）
  luo-storytelling.md           罗振宇叙事引擎：递进否定 / 讲故事六招 / 金句八法
  genre-emotion-map.md          按题材选结构、排情绪、找范本
  scorecard.md                  叙事六维评分卡 + 安全门
```

## 安装

Claude Code / Codex 等支持 Agent Skill 的环境：把本仓库放进你的 skills 目录即可。

```bash
git clone https://github.com/wade56754/koda-youtube-scripting.git ~/.claude/skills/koda-youtube-scripting
```

触发词：「写 YouTube 逐字稿」「YouTube 口播」「油管视频稿」。

## 需要自备的东西

- **叙事范本语料**：本仓库只含方法论和期数索引，不含罗辑思维逐字稿本体（版权原因）。范本通读环节需要你自备公开节目转录
- **品牌 voice 文件**：你自己的定位、表达风格、禁用词表（step04/step05 引用，路径按你的知识库配置）

## 边界

- 本 skill 蒸馏公开节目的叙事结构用于学习，**禁止**产出冒充罗振宇的内容、虚构其第一人称经历
- 所有案例与数字必须真实可溯源，没有素材就换认知，不编造

## License

MIT
