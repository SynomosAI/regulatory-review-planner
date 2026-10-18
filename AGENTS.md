# AGENTS.md — 给 AI Agent 的工作指引

本文件面向自动化 AI Agent。人类读者请看 [README.md](README.md)。

## 这个仓库是什么

`regulatory-review-planner` 是一个 **Agent Skill 发布包**，在 WorkBuddy 中对中文政策/制度草稿做规划式合规审查。核心资产是 `SKILL.md`（YAML frontmatter + 全量方法），辅以 `references/` 审查分类与策略、`scripts/split_articles.mjs` 条文拆分、`agents/openai.yaml` 接入配置。

## 可用的工作命令

```bash
# 查看技能元数据
head -15 SKILL.md

# 拆分长制度文本为条文数组
node scripts/split_articles.mjs 你的制度.txt

# 查看审查分类
grep -n "层\|必查\|专项" references/review-taxonomy.md
```

前置依赖：Node.js（跑 split_articles.mjs）；技能主体在 WorkBuddy 内运行。

## 约定（Do）

- 修改前先读 `SKILL.md` frontmatter，保持 `name`/`version`/`author`/`license` 兼容。
- 修改审查分类时同步更新 `references/review-taxonomy.md`、`SKILL.md` 与本 README 速查表。
- 新增 MCP 能力时先在 `references/tool-integration-policy.md` 登记。

## 禁止（Don't）

- 不要改动 `SKILL.md` 的 `author`/`license` 字段与 `LICENSE.md` 版权主体（© 2026 注册老炮@MedXpert）——**权属字段只由维护者变更**。
- 不要编造未授权的 MCP 能力；未实际调用成功不得写「已核验」。
- 不要在仓内提交真实制度草稿、企业主体数据、密钥或令牌。
- 不要声称本仓「已认证 / 已商用交付 / 已服务特定客户」或给出正式法律意见。

## 边界

本仓专注**中文制度合规审查方法**；不替代正式法律意见，不覆盖境外法规。企业主体状态需人工核验。
