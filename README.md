# My Skills Collection

本仓库收集了本地使用的各种AI助手Skills，包括OpenCode和Claude Code的Skills。

## ⭐ 重点推荐：Superpowers

**Superpowers** 是OpenCode中最强大的Skills集合，专门用于提升开发效率和工作质量。它们是**元技能**——帮助你更好地使用AI进行开发。

### 为什么 Superpowers 如此特别？

| 特性 | 说明 |
|------|------|
| 🚀 **效率提升** | 系统化流程避免重复踩坑 |
| 🎯 **质量保证** | 标准化验证确保交付质量 |
| 🧠 **最佳实践** | 汇聚资深工程师经验 |
| 🔄 **可扩展** | 可创建自定义Superpower |

---

## 📁 目录结构

```
my_skills/
├── README.md                    # 本说明文档
├── opencode_skills/             # OpenCode 工具Skills
│   ├── gog/                   # Google Workspace CLI
│   ├── opentwitter/            # Twitter/X API
│   ├── tiktok-automation/     # TikTok自动化
│   └── videodb/               # 视频理解与处理
│
├── opencode_superpowers/       # ⭐ OpenCode Superpowers (重点!)
│   ├── using_superpowers/     # 如何使用Superpowers
│   ├── brainstorming/          # 头脑风暴
│   ├── systematic_debugging/   # 系统化调试
│   ├── test_driven_development/ # 测试驱动开发
│   ├── writing_plans/          # 编写计划
│   ├── verification_before_completion/ # 完成前验证
│   ├── subagent_driven_development/ # 子代理开发
│   ├── dispatching_parallel_agents/ # 并行代理
│   ├── using_git_worktrees/   # Git Worktrees
│   ├── finishing_a_development_branch/ # 分支完成
│   ├── requesting_code_review/ # 请求代码审查
│   ├── receiving_code_review/  # 接收代码审查
│   └── writing_skills/        # 创建Skills
│
└── claude_code_skills/        # Claude Code Skills
    ├── token-efficiency/       # Token效率优化
    ├── jupyter-notebook/       # Jupyter分析
    ├── data-visualization/     # 数据可视化
    ├── vgp-pipeline/          # VGP基因组组装
    └── ... (更多)
```

---

## 🚀 Superpowers 详解

### 核心Superpowers

#### 1. `using_superpowers` - Superpowers使用指南
> **必读！** 了解如何正确使用Superpowers系统

```markdown
# 核心规则
如果你认为有1%的可能性某个skill适用，你必须调用它。
```

#### 2. `brainstorming` - 头脑风暴
- **何时使用**: 任何创造性工作前（创建功能、构建组件、添加功能）
- **作用**: 探索用户意图、需求和设计
- **文档**: [brainstorming/SKILL.md](opencode_superpowers/brainstorming/SKILL.md)

#### 3. `systematic_debugging` - 系统化调试
- **何时使用**: 遇到任何bug、测试失败或意外行为
- **作用**: 结构化调试方法论，而非随机尝试
- **文档**: [systematic_debugging/SKILL.md](opencode_superpowers/systematic_debugging/SKILL.md)

#### 4. `test_driven_development` - 测试驱动开发
- **何时使用**: 实现任何功能或修复bug之前
- **作用**: 先写测试，再写实现，确保测试通过
- **文档**: [test_driven_development/SKILL.md](opencode_superpowers/test_driven_development/SKILL.md)

#### 5. `writing_plans` - 编写计划
- **何时使用**: 有规范或需求文档的多步骤任务
- **作用**: 创建详细的实现计划
- **文档**: [writing_plans/SKILL.md](opencode_superpowers/writing_plans/SKILL.md)

#### 6. `verification_before_completion` - 完成前验证
- **何时使用**: 声称工作完成、修复、测试通过之前
- **作用**: 证据优先，验证后再断言
- **文档**: [verification_before_completion/SKILL.md](opencode_superpowers/verification_before_completion/SKILL.md)

### 高级Superpowers

#### 7. `subagent_driven_development` - 子代理开发
- **何时使用**: 执行有独立任务的实现计划
- **作用**: 多代理并行执行，提高效率

#### 8. `dispatching_parallel_agents` - 并行代理分发
- **何时使用**: 面对2+个独立任务时
- **作用**: 并行执行而非串行

#### 9. `using_git_worktrees` - Git Worktrees
- **何时使用**: 开始需要与当前工作隔离的特性工作
- **作用**: 创建隔离的git worktree

#### 10. `finishing_a_development_branch` - 分支完成
- **何时使用**: 实现完成、测试通过，需要决定如何集成工作
- **作用**: 提供合并/PR/清理的结构化选项

#### 11-14. 代码审查相关
- `requesting_code_review` - 请求代码审查
- `receiving_code_review` - 接收代码审查反馈

#### 15. `writing_skills` - 创建Skills
> **重点！** 教你如何创建自己的Skills

---

## 📝 创建自己的 Skill

### 使用 skill-creator

OpenCode提供了专门的 `skill-creator` skill来帮助你创建Skills：

```bash
# 在OpenCode中使用
使用 skill-creator skill
```

### SKILL.md 标准格式

```markdown
---
name: my-awesome-skill
description: Use when [具体的触发条件和使用场景]
---

# 我的Awesome技能

## 何时使用

- 场景1
- 场景2

## 核心概念

### 概念1

详细说明...

## 快速参考

| 操作 | 命令 |
|------|------|
| 示例1 | xxx |

## 示例

```bash
# 示例代码
```
```

### Frontmatter 必需字段

| 字段 | 说明 | 示例 |
|------|------|------|
| `name` | 技能名称（字母、数字、连字符） | `my-skill-name` |
| `description` | 触发条件，以"Use when"开头 | `Use when implementing...` |

### 关键原则

1. **描述 = 触发条件，而非工作流程**
   - ❌ 不好: `description: Use for TDD - write test first, then code`
   - ✅ 更好: `description: Use when implementing any feature or bugfix, before writing implementation code`

2. **TDD原则**: 先写测试，再写Skill
   - 先运行没有Skill的场景，观察失败
   - 编写Skill解决问题
   - 验证Skill有效

3. **简洁优先**: 
   - 获取-started工作流: <150词
   - 常用Skills: <200词
   - 其他: <500词

### Skill 目录结构

```
skill-name/
├── SKILL.md              # 必须
├── references/           # 可选：参考资料
│   └── detail.md
├── scripts/              # 可执行脚本
│   └── helper.sh
└── assets/               # 静态资源
    └── template.png
```

---

## 🎯 实战示例：使用 skill-creator 创建 Skill

下面我们通过一个完整的示例，展示如何使用 skill-creator 创建一个新的 Skill。

### 示例场景

假设我们要创建一个 `pdf-organizer` Skill，用于帮助用户整理PDF文件（重命名、分类、移动到对应文件夹等）。

### 步骤1：启动 skill-creator

```
使用 skill-creator skill
```

skill-creator 会引导你完成以下流程：

### 步骤2：理解需求

skill-creator 会问你一些问题来确定Skill的功能：

```
我: 我想创建一个整理PDF文件的skill

skill-creator: 好的，让我帮你创建这个skill。请回答几个问题：

1. 这个skill支持什么功能？
   - 重命名PDF文件
   - 按日期/类型分类
   - 移动到对应文件夹
   - 其他？

2. 能给几个具体使用例子吗？
   - 比如："帮我把下载文件夹里的发票都移到 receipts/ 文件夹"
   - 或者："按日期重命名这些合同PDF"

3. 用户说什么时会触发这个skill？
   - "整理PDF"
   - "移动PDF"
   - 等等
```

### 步骤3：初始化 Skill

确定需求后，运行初始化脚本：

```bash
# 创建新skill目录
scripts/init_skill.py pdf-organizer --path ./skills
```

这会生成以下结构：

```
pdf-organizer/
├── SKILL.md                    # 主文件（模板）
├── references/
│   └── example.md              # 示例文件（可删除）
├── scripts/
│   └── organize.py             # 脚本示例（可删除）
└── assets/
    └── template.png            # 资源示例（可删除）
```

### 步骤4：编辑 SKILL.md

根据需求，编辑生成的 SKILL.md：

```markdown
---
name: pdf-organizer
description: Use when user needs to organize, rename, move, or categorize PDF files. Examples: "organize PDFs by date", "move all invoices to receipts folder", "rename contracts by client name".
---

# PDF Organizer

## 功能

- 按日期整理PDF
- 按类型/类别分类
- 批量重命名
- 移动到指定文件夹

## 使用方法

### 基本命令

| 操作 | 命令 |
|------|------|
| 按日期整理 | `python scripts/organize.py --by-date /path/to/pdfs` |
| 按类型分类 | `python scripts/organize.py --by-type /path/to/pdfs` |
| 批量重命名 | `python scripts/rename.py --pattern "{date}_{title}" /path/to/pdfs` |

### 示例

```bash
# 按修改日期整理
python scripts/organize.py --by-date ~/Downloads

# 将发票移动到receipts文件夹
python scripts/organize.py --move-type invoice --dest ~/Documents/receipts

# 按合同方重命名
python scripts/rename.py --pattern "{client}_{date}" --client-map clients.csv contract/
```
```

### 步骤5：验证并打包

```bash
# 验证skill
scripts/package_skill.py pdf-organizer

# 如果验证通过，会生成 pdf-organizer.skill 文件
```

### 完整流程图

```
┌─────────────────────────────────────────────────────────┐
│                    skill-creator 工作流                  │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  1. 启动                                               │
│     └─→ 使用 skill-creator skill                        │
│                                                         │
│  2. 理解需求                                           │
│     ├─ 这个skill支持什么功能？                           │
│     ├─ 给几个使用例子？                                  │
│     └─ 什么情况下触发？                                  │
│                                                         │
│  3. 初始化                                             │
│     └─→ scripts/init_skill.py <name> --path <path>    │
│                                                         │
│  4. 编辑                                               │
│     ├─ 编写 SKILL.md                                    │
│     ├─ 添加 scripts/ (可选)                              │
│     ├─ 添加 references/ (可选)                           │
│     └─ 添加 assets/ (可选)                              │
│                                                         │
│  5. 验证打包                                           │
│     └─→ scripts/package_skill.py <skill-folder>        │
│                                                         │
│  6. 迭代优化                                           │
│     └─→ 测试 → 改进 → 再次测试                          │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### 常用命令速查

| 命令 | 说明 |
|------|------|
| `init_skill.py <name>` | 创建新的skill模板 |
| `package_skill.py <path>` | 验证并打包skill |
| `edit_skill.py <path>` | 编辑现有skill |

---

## 📥 安装说明

### 方式一：克隆到本地

```bash
# 使用SSH克隆
git clone git@github.com:hzm8341/my_skills.git ~/my_skills

# 或使用HTTPS
git clone https://github.com/hzm8341/my_skills.git ~/my_skills
```

### 方式二：复制到OpenCode

```bash
# 复制Superpowers到OpenCode
cp -r opencode_superpowers/* ~/.config/opencode/skills/superpowers/

# 复制工具Skills
cp -r opencode_skills/* ~/.agents/skills/
```

### 方式三：复制到Claude Code

```bash
# 设置环境变量
export CLAUDE_METADATA="$HOME/my_skills/claude_code_skills"

# 创建符号链接
cd ~/your-project
mkdir -p .claude/skills
ln -s ~/my_skills/claude_code_skills/* .claude/skills/
```

---

## 🔧 使用方法

### 在OpenCode中使用

#### 自动激活
OpenCode会根据任务自动激活相关Superpower：
- 遇到bug → 自动激活 `systematic-debugging`
- 写代码前 → 自动激活 `test-driven-development`
- 多步骤任务 → 自动激活 `writing_plans`

#### 手动激活
```
使用 brainstorming skill
使用 systematic-debugging skill
使用 writing-plans skill
```

### Superpowers工作流示例

```
用户: 帮我实现一个用户登录功能

→ 自动触发 brainstorming
  → 明确需求: 登录方式、验证逻辑、错误处理

→ 自动触发 test-driven-development
  → 先写测试: 测试登录成功、失败、边界情况

→ 实现功能
  → 编写登录逻辑

→ 自动触发 verification_before_completion
  → 验证: 测试通过? 边界情况? 代码质量?

→ 完成后
  → 可能触发 requesting-code-review
```

---

## 📚 其他Skills

### OpenCode 工具Skills

| Skill | 功能 | 环境变量 |
|-------|------|----------|
| gog | Google Workspace CLI | 需要OAuth |
| opentwitter | Twitter/X API | TWITTER_TOKEN |
| tiktok-automation | TikTok自动化 | Rube MCP |
| videodb | 视频处理 | VIDEO_DB_API_KEY |

### Claude Code Skills

| Skill | 功能 |
|-------|------|
| token-efficiency | Token优化 |
| jupyter-notebook | 数据分析 |
| data-visualization | 可视化 |
| vgp-pipeline | 基因组组装 |
| galaxy-automation | 工作流自动化 |

---

## 🔄 更新Skills

```bash
cd ~/my_skills
git pull origin main
```

---

## ⚠️ 注意事项

1. **始终使用Superpowers**: 如果不确定用什么，优先使用相关的Superpower
2. **先测试再部署**: 创建新Skill时，遵循TDD原则
3. **符号链接**: 推荐使用符号链接，便于统一更新
4. **按需激活**: 不需要激活所有Skills

---

## 🤝 贡献

欢迎提交Issue和Pull Request来改进这个Skills集合！

---

## 📄 许可证

MIT License

---

*Generated on 2026-03-13*
