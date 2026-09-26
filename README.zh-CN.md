# Top Conference Paper Writing

[English](README.md) · [简体中文](README.zh-CN.md)

一个用于起草、修改与检查科研论文的 Codex skill，适用于机器学习、计算机视觉、自然语言处理、机器人及相关领域。它围绕研究问题、贡献、方法与证据组织论文，并遵守每次任务的实际范围：既可处理整篇稿件，也可只补一个引用或修改一句话。

**Skill 名称：** `topconference-paperwriting`

**在 Codex 中调用：** `$topconference-paperwriting`

## 覆盖哪些任务

[SKILL.md](SKILL.md) 是总入口，规定任务范围、证据处理、写作原则和交付检查，再按任务需要读取对应章节。各指南覆盖实证、理论、系统和基准类论文，不强制套用同一种论文结构或某个会议的行文风格。

| 任务 | 支持内容 |
|---|---|
| 起草整篇论文或单个章节 | 将已有笔记和结果组织成问题、缺口、贡献与支撑论证。 |
| 修改开篇与收尾章节 | 使标题、摘要、引言、贡献和结论与已经建立的研究结果一致。 |
| 完善方法与附录 | 澄清符号、算子范围、训练与推理的区别、假设、算法及附录引用。 |
| 组织实验叙述 | 区分基线，解读主结果与消融，核查单位和百分比变化，定义效率测量范围。 |
| 添加或核对引用 | 将来源与具体论断对应，保留正确归属，去重文献条目，支持“只加引用”。 |
| 调整 LaTeX 与交付形式 | 处理表格、图注、公式、排版，以及按要求更新中英对照 HTML 或 PDF。 |
| 检查或模拟审阅稿件 | 核对跨章节一致性，查阅当年会议规定，形成有证据依据的审稿式评估。 |

另有具身智能、视觉决策与自适应计算专题，仅在论文涉及这些内容时使用。

## 安装

先安装 Git，并使用支持本地 skills 的 Codex 环境。将本仓库克隆到用户 skills 目录。以下命令优先使用已设置的 `CODEX_HOME`；未设置时，macOS/Linux 使用 `~/.codex`，Windows 使用 `%USERPROFILE%\.codex`。

**macOS / Linux — Bash**

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/zxqing01/topconference-paperwriting.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/topconference-paperwriting"
```

**Windows — PowerShell**

```powershell
$skillRoot = if ($env:CODEX_HOME) {
    Join-Path $env:CODEX_HOME 'skills'
} else {
    Join-Path $env:USERPROFILE '.codex\skills'
}
New-Item -ItemType Directory -Force -Path $skillRoot | Out-Null
git clone https://github.com/zxqing01/topconference-paperwriting.git `
    (Join-Path $skillRoot 'topconference-paperwriting')
```

请使用实际运行该 skill 的 Codex 实例所配置的 `CODEX_HOME`。如果目标目录已经存在，应保留本地修改并更新已有副本，而不是覆盖克隆。安装后可在下一轮对话或新建的 Codex 任务中按名称调用 skill。

## 快速开始

提供当前使用的稿件或段落、相关证据，以及希望执行的操作。涉及会议要求时，注明会议、年份和投稿阶段。说明所需输出，例如修改后正文、更新的 LaTeX 文件、中英对照或审阅报告。

```text
$topconference-paperwriting
请修改附件论文的摘要，使表达更清楚、简洁。
以结果表格为证据，保留数字和论断范围。
返回修改后的英文摘要及对应中文翻译。
```

通常的使用流程是：

1. **明确当前源文件与任务范围。** 指定要修改的版本及局部限制。需要核对实现时，提供相关代码或配置。
2. **按需使用章节指南。** 局部修改读取对应指南；整篇论文任务按稿件顺序使用适用章节。
3. **依据证据修改。** 保持论断、术语、数量、符号与交叉引用一致。缺失事实放入作者备注，不编造结果填空。
4. **检查并交付所需文件。** 说明修改了哪些文件、实际完成了哪些检查。检查范围取决于改动内容和可用工具。

材料尚不完整时也可以开始。该 skill 支持先起草已有证据能够支撑的部分，并指出仍需补充的具体信息。

## 触发示例

**从研究笔记建立论文论证**

```text
$topconference-paperwriting
根据这些研究笔记、定理陈述和实验表格，提出论文提纲并起草引言。
区分已经建立的发现与计划中的实验，指出缺失的证据。
```

**只加引用，不改正文**

```text
$topconference-paperwriting
只给相关工作章节添加引用和必要的 BibTeX 条目。
逐条核查来源是否支持对应论断，保留全部正文、数字和公式。
交付修改后的源文件，另附的参考文献内容只包含真正新增的条目。
```

**只做最小局部修改**

```text
$topconference-paperwriting
请把这句话缩短一到两个词，帮助它在当前行内排下。
保留技术条件和比较基线，只给一个修改方案。
```

**对照实现检查方法**

```text
$topconference-paperwriting
对照所提供的代码与配置，检查附录中的 token 选择描述。
核对索引、候选数量和最终保留数量。
只修改附录，以及确实依赖这些改动的正文引用。
```

**修改实验叙述**

```text
$topconference-paperwriting
根据所提供的表格重写消融分析，说明每项比较回答什么问题，
核对绝对提升与相对提升。保留测量结果，
不要添加证据尚未支持的机制解释。
```

**检查投稿要求或准备审阅意见**

```text
$topconference-paperwriting
按 [会议] [年份] [投稿阶段] 检查这篇稿件，并查阅当前官方说明。
区分已确认的问题、尚待解决的问题和可选改进。
暂不修改稿件文件。
```

## 修改边界与偏好配置

以明确的任务指令为准。“只加引用”只允许加入引用命令和必要的文献条目，保留现有正文与数学内容。“只改必要问题”应将可选润色单独列出。解释或评估请求不自动授权文件修改。句子级任务保持在句子级范围内，只处理必要的关联修复。

[作者偏好](references/author-defaults.md) 说明如何按需配置讨论语言、正文语言、修改范围、时态与语态、对照布局和交付形式。这些是每位作者或每个项目自行采用的选项，不绑定某个人的偏好。可将长期偏好写入简短的项目说明，并将私人稿件信息留在项目内，不加入共享 skill。当前任务的明确指令优先于此前默认值。

需要中英修订对照 HTML 时，默认原文在左、修改稿在右，英文在上、对应中文在下。也可以指定其他布局，或只输出英文。

## 工具与核验

本仓库提供 Markdown 指令，不内置自动编译器、论文查错程序或文献数据库。运行环境应按任务提供相应能力：

| 所需任务 | 必要资源 |
|---|---|
| 正文修改 | 相关段落，以及足以保持原意的上下文和证据。 |
| 引用或会议规定核查 | 可访问原始来源和当前官方说明的网络，或已提供的权威源文档。 |
| 实现核验 | 相关代码、实际生效的配置，以及核对已报告运行所需的记录。 |
| LaTeX 编译 | 完整项目文件、所需 LaTeX/参考文献工具，以及项目的构建流程。 |
| PDF 版面核验 | 编译后的 PDF，以及页面渲染和查看工具。 |

**源文件检查、编译和视觉检查验证的是不同事情。** 修改 LaTeX 源码不能证明最终换行已经符合预期；编译成功也不能证明数学正确或符合会议全部要求。该 skill 要求明确区分这些检查，并说明尚无法完成的检查。

会议规定必须对应具体的**会议、年份和阶段**核查。页数限制、匿名要求、附录位置和必需声明都不是该 skill 中永久固定的默认规则。

## 文件导航

| 文件 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 总入口、任务边界、证据原则和章节路由。 |
| [opening-sections.md](references/opening-sections.md) | 标题、摘要、引言与贡献。 |
| [related-work-and-citations.md](references/related-work-and-citations.md) | 相关工作、来源核验、只加引用与 BibTeX。 |
| [method-and-appendix.md](references/method-and-appendix.md) | 方法、符号、算法、理论与附录组织。 |
| [ablation_and_terminology.md](references/ablation_and_terminology.md) | 实验设置、结果、消融、定性证据、效率与术语。 |
| [closing-sections.md](references/closing-sections.md) | 结论、局限、可复现性与事实声明。 |
| [latex-and-delivery.md](references/latex-and-delivery.md) | 表格、公式、排版、中英 HTML 与交付文件检查。 |
| [verification-and-review.md](references/verification-and-review.md) | 当年会议规定、稿件与代码一致性、审稿式评估。 |
| [embodied_ai_writing_patterns.md](references/embodied_ai_writing_patterns.md) | 可选的具身智能与自适应计算专题。 |
| [author-defaults.md](references/author-defaults.md) | 可选的作者与项目偏好。 |

这是一个独立写作 skill，不代表任何会议的官方产品或政策，也不保证录用。研究有效性、来源准确性和最终投稿内容仍由作者负责。
