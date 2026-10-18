# regulatory-review-planner · 监管评审规划器

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
![Skill](https://img.shields.io/badge/type-Agent%20Skill-blue.svg)
![Domain](https://img.shields.io/badge/domain-Chinese%20policy%20%7C%20compliance-4f8cff.svg)
![Version](https://img.shields.io/badge/version-1.0.0-informational.svg)
![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-3ddc97.svg)

> English overview: [README.en.md](README.en.md)

SynomosAI 四支柱体系：**身份（Identity）· 溯源（Traceability）· 治理（Governance）· 共生（Symbiosis）**——当 AI 进入商业，可信是唯一的硬通货。

> 本仓库属于 [SynomosAI](https://github.com/SynomosAI) 生态技能包的一员。生态全景见 [`synomosai-skills`](https://github.com/SynomosAI/synomosal-skills)，理论站位见 [`traceability-audit`](https://github.com/SynomosAI/traceability-audit)。

本技能用于在 WorkBuddy 中对**中文政策、制度、规章制度草稿**进行模型自主规划式合规审查：按文档类型与用户目标先规划审查范围，再调用法宝版 MCP 核验关键事实，输出含命中原文、合规判断、问题说明、依据依赖、来源标签与修改建议的结构化审查备忘录。

---

## ✨ 特性 / Features

- **规划式审查**：不机械跑全量审查项，先按文档类型与材料规划审查范围。
- **最小必查集**：制度要素完整性 / 制定依据与效力 / 权限边界 / 结构一致性 / 可操作性 / 语言文字六项必查。
- **专项审查触发**：个人信息保护、公平竞争与非歧视、劳动者权益、名称时效、上级制度冲突按需触发。
- **MCP 核验留痕**：仅用已授权法宝版 MCP，未实际调用不写「已核验」，无法核验打 `[待核验]`。
- **结构化输出**：命中原文 + 判断 + 依据 + 来源标签 + 修改建议。

---

## 🚀 快速开始 / Quick Start

> 前置：本技能在 WorkBuddy 中运行；无独立安装要求，把技能目录放入技能目录即可。

```bash
# 1. 取得技能包
git clone --depth 1 https://github.com/SynomosAI/regulatory-review-planner.git
cd regulatory-review-planner

# 2. 放入 Agent 技能目录（示例：WorkBuddy）
#    cp -r . ~/.workbuddy/skills/regulatory-review-planner/
```

跑通后直接用自然语言提交一份制度草稿，例如：「**帮我审查这份员工考勤管理办法**」「**这份采购制度有没有越权处罚条款？**」。

条文拆分辅助脚本：

```bash
# 把长制度文本拆成条文数组（Node.js）
node scripts/split_articles.mjs 你的制度.txt
```

---

## 📚 参考文件 / References

| 文件 | 说明 |
|---|---|
| `references/review-taxonomy.md` | 审查分层与审查项分类体系 |
| `references/tool-integration-policy.md` | MCP 调用与降级策略 |
| `references/legal-source-policy.md` | 法规/案例来源标签策略 |
| `references/employment-review-precision.md` | 劳动者权益审查精度规则 |
| `references/review-process.md` | 审查流程细化 |
| `references/output-guidelines.md` | 输出格式指南 |
| `agents/openai.yaml` | Agent 接入配置 |
| `scripts/split_articles.mjs` | 条文拆分脚本 |

```text
触发词示例：
  合规审查 / 制度审查 / 规章审查 / 合同管理办法审查
  个人信息保护审查 / 劳动者权益审查 / 采购制度合规 / 评审规划
```

---

## 🧩 仓库结构 / Repository layout

```text
regulatory-review-planner/
├── README.md          # 本文件（中文主说明）
├── README.en.md       # 英文版说明
├── SKILL.md           # 技能主文件（YAML frontmatter + 全量方法）
├── LICENSE.md         # MIT 许可证全文
├── CODEOWNERS         # owners
├── _skillhub_meta.json# 技能市场元数据
├── references/        # 审查分类 / 工具策略 / 来源策略 / 输出指南
├── scripts/           # split_articles.mjs 条文拆分
├── agents/            # openai.yaml 接入配置
├── llms.txt / llms-full.txt
├── AGENTS.md / SECURITY.md
└── .github/workflows/ # CI 门禁
```

---

## 仓库内容

合规评审规划器

## 元信息

- **技能名**：`regulatory-review-planner`
- **版本**：1.0.0
- **署名**：SynomosAI
- **许可**：MIT（详见仓库 LICENSE）

## 使用方式

1. 克隆本仓库或将该技能目录放入你的 Agent 技能目录（如 `~/.workbuddy/skills/`）；
2. 在 Agent 中按 `SKILL.md` 的描述触发对应能力；
3. 需要审计/合规证据的场景，参考 `SKILL.md` 内模板产出工件。

---

## License / 许可

本仓库以 **MIT** 许可证发布，全文见根目录 [`LICENSE.md`](LICENSE.md)。SKILL.md 权属（© 2026 注册老炮@MedXpert，MIT）逐字保留，未作改动。

---

## 🔒 安全 / Security

如发现安全问题，请按 [`SECURITY.md`](SECURITY.md) 私下报告。审查中涉及的真实制度草稿与企业主体信息**不要提交回本仓**。

## 🤝 贡献 / Contributing

修改审查分类或专项规则时，请同步更新 `references/review-taxonomy.md` 与 `SKILL.md` 第三节；保持 frontmatter 字段兼容。

---

## 免责声明

本仓库内容为 SynomosAI 的**理论站位与工具化探索**，不代表任何已获认证、已商业化交付或已服务特定客户的声明；文中涉及的 ISO/IEC 42001、NIST AI RMF、GB/Z 185 等外部标准与条款信息为公开资料转述，正式引用前请**独立核实**。API、授权码与形象大使等为路线图（roadmap）事项，尚未上线。审查结论仅供参考，主体信息需人工核验。
