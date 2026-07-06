# 🏛️ 北海市人民检察院第三检察部公文撰写 Skill

> Claude Code Skill — 起草、修改、润色检察机关内部公文。专为第三检察部（经济犯罪检察）业务场景量身定制。

![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-2.0.0-green)
![Skill](https://img.shields.io/badge/Claude%20Code-Skill-purple)

---

## ✨ 功能概览

支持 **9 种检察机关常用文种** 的起草、修改与润色：

| 文种 | 适用场景 |
|------|----------|
| 📋 工作汇报 | 向院领导/上级院汇报工作开展情况 |
| 📨 请示 | 请求批准事项（一文一事） |
| 📄 报告 | 向上级院报告工作、答复询问 |
| 📝 情况说明 | 就某一具体事项作出说明 |
| 📌 会议纪要 | 记载会议议定事项 |
| 📰 信息简报 | 报送工作动态、经验做法 |
| 🎤 领导讲话稿 | 部署性/总结性/致辞讲话 |
| ✉️ 函 | 平级单位商洽工作 |
| 🔍 案件分析材料 | 类案或个案综合分析 |

## 🚀 快速开始（Claude Code）

```bash
# 安装
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git \
  ~/.claude/skills/beihai-proc-third-dept-writing

# 启动 Claude Code 后直接说：
# "帮我写一份第三检察部2025年上半年经济犯罪检察工作汇报"
```

---

## 🤖 多 Agent 安装指南

本 Skill 兼容主流 AI Agent 平台，以下是为各平台安装的详细步骤。

### 🔹 OpenClaw 安装

[OpenClaw](https://github.com/openclaw/openclaw) 是一个开源 AI Agent 框架。

#### 方式一：ClawHub CLI 安装（推荐）

```bash
# 从 GitHub 仓库安装
clawhub install github:Ricardo0729/third-proc-writing-skill \
  --name beihai-proc-third-dept-writing

# 或从本地安装
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git
clawhub install ./third-proc-writing-skill --name beihai-proc-third-dept-writing

# 验证安装
clawhub list | grep beihai-proc
```

#### 方式二：openclaw skills 命令安装

```bash
# 从本地路径安装
openclaw skills install /path/to/third-proc-writing-skill \
  --name beihai-proc-third-dept-writing

# 安装到所有 Agent（全局）
openclaw skills install /path/to/third-proc-writing-skill --global

# 查看已安装
openclaw skills list
# 重启 Gateway 使生效
openclaw gateway restart
```

#### 方式三：手动复制安装

```bash
# 克隆仓库
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git

# 复制到共享技能目录（所有 Agent 可用）
cp -r third-proc-writing-skill ~/.openclaw/skills/beihai-proc-third-dept-writing

# 或复制到工作区（仅当前 Agent 可用）
cp -r third-proc-writing-skill ~/.openclaw/workspace/skills/beihai-proc-third-dept-writing
```

#### 方式四：对话安装

直接在 OpenClaw 聊天窗口输入：

```
请帮我安装检察公文撰写技能，从 https://github.com/Ricardo0729/third-proc-writing-skill
```

---

### 🔹 Hermes Agent 安装

[Hermes Agent](https://github.com/NousResearch/hermes-agent) 支持标准化的 skill 安装机制。

#### 方式一：npx skills CLI（推荐，跨 Agent 通用）

```bash
# 初始化 skills.sh（首次使用）
npx skills init

# 从 GitHub 安装本技能
npx skills add Ricardo0729/third-proc-writing-skill \
  --skill beihai-proc-third-dept-writing -a hermes -g

# 查看已安装技能
npx skills list
```

> `-g` 安装到用户全局目录 `~/.agents/skills/`，对所有 Agent 生效。

#### 方式二：Hermes 原生命令行

```bash
# 直接从 GitHub 安装
hermes skills install github:Ricardo0729/third-proc-writing-skill

# 或从本地路径安装
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git
hermes skills install ./third-proc-writing-skill

# 验证
hermes skills list | grep beihai-proc
```

#### 方式三：手动复制 + external_dirs 配置

```bash
# 克隆仓库
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git

# 复制到外部技能目录
mkdir -p ~/.agents/skills
cp -r third-proc-writing-skill ~/.agents/skills/beihai-proc-third-dept-writing

# 在 ~/.hermes/config.yaml 中添加：
# skills:
#   external_dirs:
#     - ~/.agents/skills

# 验证安装
hermes skills list | grep beihai-proc
```

---

### 🔹 Kimi Work 安装

[Kimi Work](https://kimi.com) 是月之暗面推出的通用型本地 Agent。

#### 方式一：通过技能面板安装（推荐）

1. 打开 Kimi 客户端，点击左侧导航栏进入 **【Work】** 模式
2. 点击左侧的 **【技能】** 面板
3. 点击 **【安装技能】** 按钮
4. 选择 **【从 GitHub 安装】**
5. 输入仓库地址：`https://github.com/Ricardo0729/third-proc-writing-skill`
6. 点击 **【安装】** 完成

#### 方式二：手动复制安装

```bash
# 克隆仓库
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git

# 用户级安装（全局生效，推荐）
cp -r third-proc-writing-skill ~/.kimi/skills/beihai-proc-third-dept-writing

# 或标准 agents 目录（跨 Agent 通用）
cp -r third-proc-writing-skill ~/.agents/skills/beihai-proc-third-dept-writing
```

#### 方式三：在 Kimi Claw 中安装

1. 进入 Kimi Claw 的 **技能** 入口
2. 点击 **下载到 Claw**
3. 选择 **从 URL 安装**，输入：`https://github.com/Ricardo0729/third-proc-writing-skill`

#### 方式四：通过 npx skills 安装

```bash
npx skills init
npx skills add Ricardo0729/third-proc-writing-skill -g
npx skills list
```

---

### 🔹 Marvis（腾讯马维斯）安装

[Marvis](https://marvis.qq.com/) 是腾讯推出的操作系统级 AI 助手，支持 Windows/macOS/Android/iOS 全平台。

#### 方式一：从灵感广场安装（推荐）

1. 打开 Marvis 客户端，登录（微信/QQ 扫码）
2. 点击 **灵感广场**（技能广场）
3. 搜索 **"检察公文"** 或 **"公文撰写"**
4. 找到本技能卡片，点击 **一键安装**

#### 方式二：手动复制安装

```bash
# 克隆仓库
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git

# 复制到 Marvis 技能目录
cp -r third-proc-writing-skill ~/.marvis/skills/beihai-proc-third-dept-writing

# 或使用标准 agents 目录（跨 Agent 通用）
cp -r third-proc-writing-skill ~/.agents/skills/beihai-proc-third-dept-writing
```

#### 方式三：WPS 灵犀 Claw 迁移

如果已在其他 Agent 中使用过本 Skill，可直接迁移：

```bash
cp -r ~/.claude/skills/beihai-proc-third-dept-writing \
  ~/.marvis/skills/beihai-proc-third-dept-writing
```

#### 方式四：通过 npx skills 安装

```bash
npx skills init
npx skills add Ricardo0729/third-proc-writing-skill -g
```

#### 使用提示

Marvis 支持 **效率模式**（云端模型，推荐日常使用）和 **本地模式**（纯本地，适合处理敏感文件）。涉及案件材料建议切换到 **本地模式**。

---

### 🔹 Codex 安装

[Codex](https://openai.com/codex) 是 OpenAI 的 AI 代码助手，使用标准化的 Agent Skills 系统。

#### 方式一：npx skills CLI 安装（推荐）

```bash
# 安装本技能到用户全局
npx skills add Ricardo0729/third-proc-writing-skill \
  --skill beihai-proc-third-dept-writing -a codex -g

# 查看已安装
npx skills list
```

#### 方式二：手动复制安装

Codex 会自动扫描以下目录中的 skill：

```bash
# 克隆仓库
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git

# 用户级安装（全局生效，推荐）
mkdir -p ~/.agents/skills
cp -r third-proc-writing-skill ~/.agents/skills/beihai-proc-third-dept-writing

# 项目级安装（仅当前项目）
mkdir -p .agents/skills
cp -r third-proc-writing-skill .agents/skills/beihai-proc-third-dept-writing
```

> **路径说明**：Codex 新版使用 `~/.agents/skills/`，旧版使用 `~/.codex/skills/`。推荐使用 `~/.agents/skills/`。

#### 方式三：使用符号链接（开发调试用）

```bash
git clone https://github.com/Ricardo0729/third-proc-writing-skill.git \
  ~/.codex/beihai-proc-skill
mkdir -p ~/.agents/skills
ln -s ~/.codex/beihai-proc-skill ~/.agents/skills/beihai-proc-third-dept-writing
```

#### 方式四：使用 $skill-installer（Codex 内置）

在 Codex 对话中直接输入：

```
$skill-installer https://github.com/Ricardo0729/third-proc-writing-skill
```

Codex 会自动下载并安装。

---

## 🧠 核心设计理念

| 理念 | 说明 |
|------|------|
| **事实为本** | 不编造任何事实、数据、法律依据 |
| **不确定即标注** | 缺失内容使用 `【待补充】` 占位 |
| **先提纲后正文** | 确认方向再动笔，降低返修成本 |
| **输出三件套** | 提纲 + 正式稿 + 自查清单 |
| **风险隔离** | R1-R9 九条硬性约束，从源头防控 |

## 📁 项目结构

```
third-proc-writing-skill/
├── SKILL.md                  # 核心导航（渐进式披露）
├── README.md                 # 本文件
├── CHANGELOG.md              # 版本历史
├── LICENSE                   # MIT 开源许可
├── references/               # 写作参考规范（20 份文件）
│   ├── 快速入门指南.md       # 新手 3 分钟上手
│   ├── 文种速查表.md         # 文种对照速查
│   ├── 自查清单.md           # 100+ 项质量检查
│   ├── 文种规则.md           # 9 文种写作规范
│   ├── 标题模式.md           # 各文种标题格式
│   ├── 风格规则.md           # 句式与用词规范
│   ├── 常用表达.md           # 句式库 + 部门术语
│   ├── 风险规则.md           # R1-R9 详解
│   ├── 公文排版规范-GBT9704-2012.md
│   └── ……（更多参考文件）
├── templates/                # 文种模板（15 份）
│   ├── 工作汇报模板.md       # 含示例和错误分析
│   ├── 请示模板.md           # 含 3 示例 + 常见错误
│   ├── 会议纪要模板.md       # 含完整示例
│   ├── 案件分析材料模板.md   # 类案 + 个案双模板
│   └── ……
└── tests/                    # 评估用例
    ├── 评估用例.md
    └── eval/                 # 按文种分类评估
```

## 📖 使用路径

新手从这里开始：

**1️⃣ 阅读** `references/快速入门指南.md` — 3 分钟了解基本操作
**2️⃣ 查看** `references/文种速查表.md` — 根据需求定位文种
**3️⃣ 选择** `templates/` 中的对应模板 — 按模板框架填充内容
**4️⃣ 套用** `references/常用表达.md` — 规范用语不再愁
**5️⃣ 检查** `references/自查清单.md` — 100+ 项逐一把关

## 🛡️ 风险边界（R1-R9）

| 编号 | 规则 | 说明 |
|------|------|------|
| R1 | 不得虚构事实 | 无依据内容一律【待补充】 |
| R2 | 不得虚构数据 | 数字/比例/排名不得编造 |
| R3 | 不得编造法律依据 | 引用法条须标注【请核实原文】 |
| R4 | 不得代替案件结论 | 不写"经审查认为"等决定性结论 |
| R5 | 不得泄露敏感信息 | 脱敏处理：某某、某号 |
| R6 | 不得输出涉密内容 | 不写侦查手段、技侦证据 |
| R7 | 不得过度宣传 | 不使用"成效显著"等宣传腔 |
| R8 | 不得给出办案建议 | 不代替检察官定罪量刑 |
| R9 | 不得模仿特定领导语气 | 讲话稿使用模板化语气 |

## 🤝 贡献

欢迎通过 Issue 和 PR 贡献示例、模板和优化建议。涉及案件材料必须脱敏。

## 📄 许可

MIT License — 详见 [LICENSE](LICENSE) 文件。
