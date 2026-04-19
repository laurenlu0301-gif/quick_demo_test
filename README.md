# 🧠 PM Workflow Skills

> 一套面向产品经理的 AI Agent Skill 库，覆盖产品完整生命周期。
> 基于 Claude Agent Skills 规范构建，可直接在 Claude Code / Claude.ai 中调用。

---

## 📖 背景

作为产品经理，我在实际工作中探索用 AI 工具提升产品研发效率。这个仓库是我在真实项目中沉淀下来的 **Skill 集合**——不是提示词模板，而是可复用的、有明确触发条件和输出规范的 Agent Skill。

每一个 Skill 都经过真实项目验证，包含我踩过的坑和总结出的最佳实践。

---

## 🗂️ Skill 清单

| # | Skill 名称 | 阶段 | 状态 |
|---|-----------|------|------|
| 01 | [PRD 撰写](./01-prd-writing/SKILL.md) | 需求阶段 | ✅ 可用 |
| 02 | [机会定义](./02-opportunity-definition/SKILL.md) | 构思阶段 | 🚧 建设中 |
| 03 | [原型验证任务拆解](./03-prototype-task-breakdown/SKILL.md) | 验证阶段 | ✅ 可用 |
| 04 | [埋点方案设计](./04-analytics-tracking/SKILL.md) | 上线筹备 | 🚧 建设中 |
| 05 | [A/B 测试方案](./05-ab-test-setup/SKILL.md) | 迭代阶段 | 🚧 建设中 |

---

## 🚀 如何使用

### 方式一：Claude.ai 网页版（推荐新手）

1. 打开对应 Skill 的 `SKILL.md` 文件
2. 复制全部内容，粘贴给 Claude
3. 说："请按照以上 Skill，帮我处理以下需求：[你的需求]"

### 方式二：Claude Code（推荐进阶）

将本仓库 clone 到本地项目目录，Claude Code 会自动识别并加载 Skill：

```bash
git clone https://github.com/你的用户名/pm-workflow-skills.git
```

---

## 💡 核心 Skill 介绍

### 03 · 原型验证任务拆解

**解决的问题：** PM 有了方案，想快速搭可交互原型验证假设，但从 PRD 到给 AI 编程工具的执行指令之间有一道鸿沟。

**这个 Skill 做什么：**
- 自动判断后端复杂度，推荐合适的技术方案（纯 Mock / Coze 工作流 / 真实后端）
- 输出可直接粘贴到 Coze 各节点的配置内容（含 System Prompt）
- 生成针对 NoCode / Cursor / Claude Code 的专属执行指令
- 内置验收 Checklist

**支持工具组合：**
- 前端：NoCode（美团）/ Lovable / Cursor / Claude Code
- 后端：Coze 工作流 / Supabase

[→ 查看完整 Skill 文档](./03-prototype-task-breakdown/SKILL.md)

---

## 🛠️ 真实项目案例

以下是我用这套 Skill 体系实际构建过的工具，作为 Skill 有效性的验证：

### AI 简历优化工具
- **验证假设：** 用 AI 优化简历的体验能否好过用户自己改
- **技术栈：** Lovable 前端 + Supabase Edge Functions + Gemini Flash
- **用到的 Skill：** PRD 撰写 → 原型验证任务拆解
- **踩坑记录：** Gemini Flash 返回 JSON 时会带 markdown 包裹，需要两层 parse（已写入 Skill 踩坑清单）

### DPST 认知评测工具
- **验证假设：** 数字-符号替换测试能否在 Web 端流畅还原
- **技术栈：** NoCode（美团）前端
- **用到的 Skill：** 原型验证任务拆解
- **功能：** 随机符号排列、计时、网格布局自适应

---

## 📐 Skill 规范说明

本仓库遵循 [Claude Agent Skills](https://docs.claude.com) 规范，每个 Skill 包含：

```
skill-name/
├── SKILL.md        # 核心文件：触发条件、输入输出、执行步骤、踩坑记录
├── templates/      # 可复用的空白模板
└── examples/       # 真实项目的完整输出示例
```

---

## 🗺️ Roadmap

- [ ] 补全 02 机会定义 Skill
- [ ] 补全 04 埋点方案 Skill
- [ ] 补全 05 A/B 测试方案 Skill
- [ ] 为 03 添加完整的简历优化工具示例（examples/）
- [ ] 探索 Skill 链式调用：PRD → 原型任务包 一键生成

---

## 👤 关于作者

产品经理，正在探索 PM + AI Agent + Vibe Coding 的工作方式。

这个仓库是我学习和实践过程的真实记录，持续迭代中。

---

*Last updated: 2026-04*
