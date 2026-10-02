<div align="center">

![土壤试验方法顾问](docs/banner.svg)

# 土壤试验方法顾问

**从测量对象出发，找到有出处的实验方法。**

![Agent Skills](https://img.shields.io/badge/Agent_Skills-compatible-81702b?style=flat-square)
![版本](https://img.shields.io/badge/技能版本-v1-81702b?style=flat-square)
![中文](https://img.shields.io/badge/说明-中文-81702b?style=flat-square)
[![GitHub Release](https://img.shields.io/github/v/release/SoMic520/soil-methods-consultant?style=flat-square&label=下载&color=81702b)](https://github.com/SoMic520/soil-methods-consultant/releases/latest)

[功能介绍](#能帮你做什么) · [安装步骤](#安装步骤) · [使用示例](#使用示例) · [技能规则](skills/soil-methods-consultant/SKILL.md) · [下载发布包](https://github.com/SoMic520/soil-methods-consultant/releases/latest)

</div>

## 这是什么

以技能内已校正的土壤分析参考资料和官方标准为依据，帮助选择方法、查清条件与公式、比较方案，并形成带完整出处的实验说明。

这是给 AI 助手使用的 **Agent Skill（技能包）**，其中包含任务规则、参考资料和辅助脚本。安装到支持技能的工具后，可以在对话中用下面的示例调用。完成任务仍需工具可用的模型及运行环境。

## 能帮你做什么

| 任务 | 具体能力 |
| --- | --- |
| **从测量对象选择方法** | 明确总量、可提取态、交换态与有效态等测量对象，结合样品条件、仪器和需求选择方法。 |
| **检索已校正资料** | 内置 6 套核心参考资料与 19 份已校对国家标准；保留原方法层级、编号、单位和公式。 |
| **核对操作与计算** | 按同一来源检查试剂用量、操作条件、结果计算与质量控制，提供方法比较和故障排查。 |
| **形成实验方案** | 根据同一条方法记录输出简要 HTML 与 A4 PDF，列出试剂仪器、步骤、计算、质控及出处。 |

## 开始前准备什么

- 待测指标及明确的测量对象
- 样品性质、仪器条件和实验目的
- 方法或标准线索、结果计算所需参数

按任务范围，通常可以获得：

- 方法推荐、比较或精确检索结果
- 带出处的步骤、公式与计算说明
- HTML / PDF 实验方案及质控要点

## 安装步骤

### 1. 准备工具

先准备 **Codex、Claude Code 或其他支持 Agent Skills 的 AI 工具**，以及 [GitHub CLI](https://cli.github.com/)。GitHub CLI 需支持 `gh skill` 命令（2.90.0 及以上；建议使用当前稳定版）。它用于下载技能。

- **Windows**：在 PowerShell 执行 `winget install --id GitHub.cli --exact`。
- **macOS**：从 [GitHub CLI 官方下载页](https://cli.github.com/) 获取安装包；已有 Homebrew 时可执行 `brew install gh`。

安装后，打开终端或 PowerShell 检查版本并登录：

```shell
gh --version
gh auth login
```

### 2. 安装到你使用的 AI 工具

以 **Codex** 为例，复制下面这一行到终端或 PowerShell 执行：

```shell
gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent codex --scope user
```

`--scope user` 表示安装到当前用户，供不同项目使用。使用其他工具时，选择对应命令：

| AI 工具 | 安装命令 |
| --- | --- |
| Codex | `gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent codex --scope user` |
| Claude Code | `gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent claude-code --scope user` |
| GitHub Copilot | `gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent github-copilot --scope user` |
| Gemini CLI | `gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent gemini-cli --scope user` |
| Cursor | `gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent cursor --scope user` |
| OpenCode | `gh skill install SoMic520/soil-methods-consultant soil-methods-consultant --agent opencode --scope user` |

安装前想先看看规则，可以执行：

```shell
gh skill preview SoMic520/soil-methods-consultant soil-methods-consultant
```

### 3. 在对话中使用

安装完成后，重新打开 AI 工具或开始新会话，提供你的材料，并明确写出 **“请使用 soil-methods-consultant……”**。从下面选一条示例，替换成你的实际任务即可。

## 使用示例

```text
请使用 soil-methods-consultant 比较适合我这批土样的有效磷测定方法。先询问样品性质、测量目的和仪器条件，再给出来源与适用边界。
```

```text
请使用 soil-methods-consultant 检索土壤有机碳测定方法。保持来源内的试剂、条件和计算公式一致，列出方法出处及质控要点。
```

```text
请使用 soil-methods-consultant 按我指定的标准生成 A4 实验方案，包含试剂仪器、步骤、结果计算与质控，并核实标准的现行状态。
```

## 使用范围

不同来源的试剂、用量、条件、公式与质控限需分别处理。内置资料有版本与适用范围；查询最新标准、替代关系或本地缺项时需要核实发布机构原文。

## 下载与更新

- [最新发布包](https://github.com/SoMic520/soil-methods-consultant/releases/latest)：适合下载、留存或按平台说明手动安装。
- [当前技能 ZIP](dist/soil-methods-consultant-skill-20260816-v1.zip) 与 [SHA-256 校验值](dist/SHA256SUMS.txt)：用于核对文件完整性。
- 更新已安装的技能：

```shell
gh skill update soil-methods-consultant
```

AI 工具与 GitHub CLI 会持续更新；命令差异请以当前工具帮助为准。`gh skill` 的安装与预览说明见 [GitHub CLI 官方文档](https://cli.github.com/manual/gh_skill)。

## 仓库结构

```text
skills/soil-methods-consultant/
  SKILL.md       技能入口与工作规则
  agents/        智能体配置
  references/    参考资料与任务规范
  scripts/       辅助脚本与校验工具
docs/banner.svg  仓库封面
dist/            技能发布包与 SHA-256 校验值
```

[阅读完整技能规则](skills/soil-methods-consultant/SKILL.md) · [查看专项参考资料](skills/soil-methods-consultant/SKILL.md) · [查看拆分记录](CHANGELOG.md)

## 其他 Hemusci 技能

| 独立仓库 | 用途 |
| --- | --- |
| [土壤科学与自然科学写作](https://github.com/SoMic520/soil-all-writing) | 从原始底稿到正式交付，让文字与证据对齐。 |
| [R 土壤学科研绘图](https://github.com/SoMic520/r-soil-scientific-figures) | 按研究问题选图，把数据、代码与图形一起交付。 |
| [土壤学期刊投稿格式审查](https://github.com/SoMic520/soil-journal-format-review) | 依照期刊官方规则，逐项检查投稿文件。 |
| [土壤三普专业报告](https://github.com/SoMic520/soil-third-survey-report) | 对齐省、市、县成果层级，整理可送审的专业报告。 |

[返回 Hemusci 技能总目录](https://github.com/SoMic520/Hemusci-Skills) · [Hemusci 网站](https://hemusci.com/skills/)

---

此仓库于 2026-10-02 从 [Hemusci-Skills](https://github.com/SoMic520/Hemusci-Skills/tree/c41529fe9fe6833ff65679133dfed24ea4d4b61c/skills/soil-methods-consultant) 拆分，保留该技能的提交历史、规则与资料。原集合继续保留兼容安装入口。

**使用与许可**：沿用原仓库的许可状态，目前未设置开源许可证；公开可见不等同于授予再发布许可。参考资料、标准及第三方内容的权利归其各自权利人。有关复制、修改、传播或再发布的授权，请联系仓库所有者。
