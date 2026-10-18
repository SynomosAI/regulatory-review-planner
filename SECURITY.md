# 安全策略 / Security Policy

## 报告安全问题

如果你发现本仓库的安全问题（例如 `scripts/split_articles.mjs` 读取路径异常、`agents/openai.yaml` 泄露配置、参考文档含敏感样例），请**私下**联系维护者：

- 邮箱：zhaoxinghua09@gmail.com
- 请在邮件中说明：问题描述、复现步骤、影响范围、你建议的修复方式。

**不要在公开 issue / PR 中披露未修复的安全问题。**

## 范围

本仓库为 **Agent Skill 发布包**（SKILL.md 方法 + references 文档 + 一个 Node.js 条文拆分脚本）。

- **网络行为**：`split_articles.mjs` 仅做本地文本处理，不发起网络请求。技能运行时通过已授权法宝版 MCP 查询法规/案例，来源由 `references/legal-source-policy.md` 约束。
- **数据**：审查中读取的真实制度草稿、企业主体信息由使用者在自己的环境中处理；本仓不持有任何真实审查数据。

## 我们的承诺

- 收到有效报告后，我们会在合理时间内确认并评估。
- 修复后会在 PR / README 变更中记录（按需脱敏）。

## 使用者须知

- 请从**本仓库官方地址**获取技能包，警惕第三方二次打包。
- **真实制度草稿、企业主体数据、客户信息不要提交回本仓**，也不要贴进公开 issue。
- 任何密钥 / 令牌都不应提交进仓库。

---

许可：MIT ｜ © 2026 注册老炮@MedXpert ｜ 联系：zhaoxinghua09@gmail.com ｜ ORCID 0009-0001-0512-1237
