# My Skills Collection

本仓库收集了本地使用的各种AI助手Skills，包括OpenCode和Claude Code的Skills。

## 目录结构

```
my_skills/
├── README.md                    # 本说明文档
├── opencode_skills/             # OpenCode 主要Skills
│   ├── gog/                   # Google Workspace CLI
│   ├── opentwitter/            # Twitter/X API
│   ├── tiktok-automation/     # TikTok自动化
│   └── videodb/               # 视频理解与处理
│
├── opencode_superpowers/       # OpenCode Superpowers
│   ├── brainstorming/
│   ├── dispatching_parallel_agents/
│   ├── executing_plans/
│   ├── finishing_a_development_branch/
│   ├── receiving_code_review/
│   ├── requesting_code_review/
│   ├── subagent_driven_development/
│   ├── systematic_debugging/
│   ├── test_driven_development/
│   ├── using_git_worktrees/
│   ├── using_superpowers/
│   ├── verification_before_completion/
│   ├── writing_plans/
│   └── writing_skills/
│
└── claude_code_skills/        # Claude Code Skills
    ├── automation/             # Galaxy自动化
    ├── collaboration/          # 团队协作
    ├── conda-recipe/          # Conda配方
    ├── data-analysis-patterns/
    ├── data-backup/
    ├── data-visualization/
    ├── documentation/
    ├── documentation-organization/
    ├── folder-organization/
    ├── frontend-slides/
    ├── fundamentals/           # 生物信息学基础
    ├── hackmd/
    ├── jupyter-notebook/
    ├── managing-environments/
    ├── obsidian/
    ├── phylogenetics/          # 系统发育学
    ├── plan-first/
    ├── project-sharing/
    ├── scientific-publication/
    ├── self-improvement/
    ├── skill-management/
    ├── token-efficiency/
    ├── tool-wrapping/
    ├── vgp-pipeline/          # VGP基因组组装
    └── workflow-development/
```

---

## 📥 安装说明

### 方式一：克隆到本地

```bash
# 使用SSH克隆
git clone git@github.com:hzm8341/my_skills.git ~/my_skills

# 或使用HTTPS
git clone https://github.com/hzm8341/my_skills.git ~/my_skills
```

### 方式二：复制到对应位置

```bash
# OpenCode Skills
cp -r opencode_skills/* ~/.agents/skills/

# OpenCode Superpowers
cp -r opencode_superpowers/* ~/.config/opencode/skills/superpowers/

# Claude Code Skills (需要设置环境变量)
export CLAUDE_METADATA="$HOME/my_skills/claude_code_skills"
```

---

## 🔧 使用说明

### OpenCode 使用方法

#### 1. 使用 Skill 工具调用

在OpenCode中，使用`Skill`工具来激活Skills：

```
使用 gog skill
使用 opentwitter skill
使用 videodb skill
```

#### 2. 自动激活

OpenCode会根据任务内容自动判断并激活相关Skill。例如：
- 遇到bug时 → 自动激活 `systematic-debugging`
- 需要测试时 → 自动激活 `test-driven-development`
- 需要规划时 → 自动激活 `writing-plans`

#### 3. 常用Skills

| Skill | 用途 |
|-------|------|
| gog | Google Workspace操作 (Gmail, Calendar, Drive, Sheets, Docs) |
| opentwitter | Twitter数据查询 |
| tiktok-automation | TikTok自动化 |
| videodb | 视频理解处理 |

---

### Claude Code 使用方法

#### 1. 环境变量设置

```bash
# 在 ~/.zshrc 或 ~/.bashrc 中添加
export CLAUDE_METADATA="$HOME/my_skills/claude_code_skills"

# 使其生效
source ~/.zshrc
```

#### 2. 创建符号链接

```bash
# 进入你的项目目录
cd ~/your-project

# 创建.claude目录
mkdir -p .claude/skills .claude/commands

# 链接常用Skills (使用符号链接)
ln -s ~/my_skills/claude_code_skills/token-efficiency .claude/skills/token-efficiency
ln -s ~/my_skills/claude_code_skills/claude-collaboration .claude/skills/claude-collaboration
ln -s ~/my_skills/claude_code_skills/jupyter-notebook .claude/skills/jupyter-notebook

# 链接所有可用Skills
for skill in ~/my_skills/claude_code_skills/*; do
    ln -s "$skill" .claude/skills/$(basename "$skill")
done
```

#### 3. 使用Skill

在Claude Code中，Skill会自动根据任务激活。你也可以手动激活：

```
Use the jupyter-notebook skill to analyze this data.
Use the data-visualization skill to create a chart.
```

---

## 📚 Skills 详解

### OpenCode Skills

#### gog - Google Workspace CLI
- **功能**: Gmail, Calendar, Drive, Sheets, Docs 命令行操作
- **安装**: 需要先安装 gog 工具: `brew install steipete/tap/gogcli`
- **设置**: 需要OAuth认证配置
- **文档**: [gog/SKILL.md](opencode_skills/gog/SKILL.md)

#### opentwitter - Twitter/X API
- **功能**: Twitter数据查询、用户信息、推文搜索、粉丝追踪
- **环境变量**: 需要设置 `TWITTER_TOKEN`
- **获取Token**: https://6551.io/mcp
- **文档**: [opentwitter/SKILL.md](opencode_skills/opentwitter/SKILL.md)

#### tiktok-automation - TikTok自动化
- **功能**: 视频上传、发布、查看profile、用户统计
- **依赖**: 需要 Rube MCP (Composio)
- **设置**: 添加 `https://rube.app/mcp` 作为MCP服务器
- **文档**: [tiktok-automation/SKILL.md](opencode_skills/tiktok-automation/SKILL.md)

#### videodb - 视频理解与处理
- **功能**: 视频索引、搜索、编辑、字幕生成、桌面录制
- **环境变量**: 需要 `VIDEO_DB_API_KEY`
- **获取API**: https://videodb.io
- **文档**: [videodb/SKILL.md](opencode_skills/videodb/SKILL.md)

---

### OpenCode Superpowers

| Skill | 功能 | 使用场景 |
|-------|------|----------|
| brainstorming | 头脑风暴 | 创造性工作前 |
| systematic-debugging | 系统调试 | 遇到bug时 |
| test-driven-development | 测试驱动开发 | 编写测试前 |
| writing-plans | 编写计划 | 多步骤任务 |
| verification_before_completion | 完成前验证 | 任务收尾 |
| subagent-driven-development | 子代理开发 | 复杂任务分解 |
| using-git-worktrees | Git Worktrees | 特性分支开发 |
| finishing-a-development-branch | 分支完成 | PR/合并前 |
| receiving-code-review | 接收代码审查 | 收到反馈后 |
| requesting-code-review | 请求代码审查 | 提交代码前 |

---

### Claude Code Skills

| Skill | 功能 | 适用场景 |
|-------|------|----------|
| token-efficiency | Token效率优化 | 节省API调用 |
| jupyter-notebook | Jupyter笔记本分析 | 数据分析 |
| data-visualization | 数据可视化 | 图表制作 |
| vgp-pipeline | VGP基因组组装 | 基因组学 |
| galaxy-automation | Galaxy工作流自动化 | 生物信息 |
| tool-wrapping | Galaxy工具封装 | Galaxy开发 |
| scientific-publication | 科学论文出版 | 论文写作 |
| obsidian | Obsidian笔记集成 | 知识管理 |
| conda-recipe | Conda配方 | 环境配置 |
| managing-environments | 环境管理 | 环境维护 |
| workflow-development | Galaxy工作流开发 | 工作流创建 |
| frontend-slides | 前端幻灯片 | 演示制作 |

---

## 🔄 更新Skills

### 手动更新

```bash
cd ~/my_skills
git pull origin main
```

### 同步到项目

```bash
# 重新链接所有Skills
cd ~/your-project
rm -rf .claude/skills/*
for skill in ~/my_skills/claude_code_skills/*; do
    ln -s "$skill" .claude/skills/$(basename "$skill")
done
```

---

## 📝 创建自定义Skill

### SKILL.md 格式

```markdown
---
name: my-skill-name
description: 简短的技能描述，说明何时激活
---

# 技能名称

## 何时使用

- 使用场景1
- 使用场景2

## 核心概念

### 概念1

详细说明...

## 示例

```bash
# 示例代码
```
```

### Frontmatter 必需字段

- `name`: 技能名称（必须与目录名一致）
- `description`: 简短描述（用于决定何时激活）

### 可选字段

- `version`: 版本号 (如 1.0.0)
- `dependencies`: 依赖工具/包

---

## ⚠️ 注意事项

1. **符号链接优先**: 推荐使用符号链接而非复制，便于统一更新
2. **环境变量**: 部分Skills需要设置环境变量：
   - `TWITTER_TOKEN` - opentwitter
   - `VIDEO_DB_API_KEY` - videodb
   - `GOG_ACCOUNT` - gog
3. **版本控制**: 建议将Skills纳入Git版本控制
4. **按需激活**: 不需要激活所有Skills，根据项目需求选择

---

## 🤝 贡献

欢迎提交Issue和Pull Request来改进这个Skills集合！

---

## 📄 许可证

MIT License

---

*Generated on 2026-03-13*
