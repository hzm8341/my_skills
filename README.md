# My Skills Collection

本仓库收集了本地使用的各种AI助手Skills，包括OpenCode和Claude Code的Skills。

## 快速导航

| 类别 | Skills数量 | 说明 |
|------|-----------|------|
| [Superpowers](#-superpowers-超级能力) | 38 | 核心开发流程Skills |
| [OpenCode工具](#opencode-工具skills) | 4 | 平台集成工具 |
| [Claude Code Skills](#claude-code-skills) | 27 | 专项任务Skills |

---

## Superpowers 超级能力

Superpowers是OpenCode中最强大的Skills集合，是**元技能**——帮你更好地使用AI进行开发。

### 分类索引

| 分类 | Skills |
|------|--------|
| [🚀 自动执行](#-自动执行) | autopilot, ralph, ultraqa, ultrawork |
| [🧠 深度分析](#-深度分析) | deep-dive, deepinit, deep-interview, tracing |
| [📋 计划与协作](#-计划与协作) | plan, ralplan, brainstorming, team |
| [🔧 配置与管理](#-配置与管理) | hud, setup, skill, project-session-manager |
| [🧪 QA与验证](#-qa与验证) | ultraqa, visual-verdict, systematic-debugging, verification-before-completion |
| [📝 代码审查](#-代码审查) | requesting-code-review, receiving-code-review |
| [🔍 研究与外部信息](#-研究与外部信息) | external-context, sciomc, ask |
| [💾 记忆与学习](#-记忆与学习) | writer-memory, learner |
| [🛠️ 开发工具](#-开发工具) | writing-skills, subagent-driven-development, dispatching-parallel-agents |
| [🔀 Git工作流](#-git工作流) | using-git-worktrees, finishing-a-development-branch |
| [🎯 TDD与质量](#-tdd与质量) | test-driven-development, writing-plans |
| [🔄 OMC生态](#-omc生态) | omc-setup, omc-doctor, omc-reference, omc-teams, release, cancel, configure-notifications, mcp-setup |
| [🎨 专业工具](#-专业工具) | ai-slop-cleaner, ccg, trace, ralplan |

---

## 🚀 自动执行

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **autopilot** | 全自主执行，从想法到代码 | 启动后自动完成整个任务 |
| **ralph** | 自我参照循环，直到任务完成 | 需要持续验证的复杂任务 |
| **ultraqa** | QA循环工作流：测试→验证→修复→重复 | 质量要求高的功能开发 |
| **ultrawork** | 并行执行引擎，高吞吐量任务完成 | 多个独立任务并行处理 |

### 使用方法
```
使用 autopilot skill
使用 ralph skill
使用 ultraqa skill
使用 ultrawork skill
```

---

## 🧠 深度分析

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **deep-dive** | 2阶段管道：追踪(因果调查) + 深度访谈(需求明确) | 复杂问题的根源分析 |
| **deepinit** | 深度代码库初始化，生成层次化AGENTS.md文档 | 新项目或陌生代码库 |
| **deep-interview** | 苏格拉底式深度访谈，数学模糊度门控 | 需求不明确时澄清需求 |
| **trace** | 证据驱动的追踪车道，多假设竞争 | 并发问题的因果追踪 |

### 使用方法
```
使用 deep-dive skill "<问题描述>"
使用 deepinit skill
使用 deep-interview skill
使用 trace skill
```

---

## 📋 计划与协作

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **plan** | 战略规划，可选访谈工作流 | 复杂项目的计划制定 |
| **ralplan** | 共识规划入口，自动门控模糊请求 | 规划前的需求确认 |
| **brainstorming** | 头脑风暴，探索意图和需求 | 任何创造性工作前 |
| **team** | N个协调代理，共享任务列表 | 多代理并行开发 |

### 使用方法
```
使用 plan skill
使用 ralplan skill
使用 brainstorming skill
使用 team skill
```

---

## 👥 Team 协调代理（重点！）

**Team** 是最强大的协作技能——用 N 个协调代理并行完成复杂任务。

### 核心特性

| 特性 | 说明 |
|------|------|
| **N 个并行代理** | 1-20 个代理同时工作 |
| **共享任务列表** | 基于 Claude Code 原生团队工具 |
| **任务依赖管理** | 支持 blocks/blockedBy 依赖链 |
| **代理通信** | 代理间通过 SendMessage 协调 |
| **Git Worktree 隔离** | 并行代理在独立分支工作，避免冲突 |
| **CLI Worker 混合** | 支持 Claude + Codex + Gemini 混合团队 |

### 命令格式

```
/team N:agent-type "任务描述"
/team "任务描述"                    # 自动选择代理数量
/team ralph "任务描述"              # 结合 Ralph 持久化循环
/team 2:codex "代码审查任务"        # 使用 Codex CLI worker
/team 2:gemini "UI设计任务"         # 使用 Gemini CLI worker
```

### 参数说明

| 参数 | 说明 | 示例 |
|------|------|------|
| **N** | 代理数量 (1-20) | `3` = 3个代理 |
| **agent-type** | 代理类型 | `executor`, `debugger`, `designer`, `codex`, `gemini` |
| **ralph** | 可选修饰符 | 包装 Ralph 持久化循环 |

### Agent 类型路由

| 任务类型 | 推荐代理 | 原因 |
|----------|----------|------|
| 迭代式多步工作 | Claude teammate | 需要工具迭代 + 团队通信 |
| 代码审查/安全审计 | CLI worker 或 specialist | 自主执行，擅长结构化分析 |
| 架构分析/规划 | architect agent | 强分析推理 + 代码库访问 |
| UI/前端实现 | designer agent | 设计专长 + 框架惯用语法 |
| 大规模文档 | writer agent | 写作专长 + 大上下文一致性 |
| 构建/测试迭代 | Claude teammate | 需要 Bash + 迭代修复循环 |

### 工作流程

```
用户: "/team 3:executor 修复所有 TypeScript 错误"
              │
              ▼
      [团队协调者 (Lead)]
              │
              ├── TeamCreate("fix-ts-errors")
              │       → lead 成为 team-lead@fix-ts-errors
              │
              ├── 分析 & 分解任务
              │       → 探索/架构产生子任务列表
              │
              ├── TaskCreate x N (每个子任务一个)
              │       → 任务 #1, #2, #3 及依赖关系
              │
              ├── 监控循环
              │       ← 代理发送 SendMessage (自动投递)
              │       → SendMessage 解除阻塞/协调
              │
              └── 完成
                      → SendMessage(shutdown_request) 给每个代理
                      → TeamDelete("fix-ts-errors")
```

### 执行管道

Team 执行遵循分阶段管道：

`team-plan → team-prd → team-exec → team-verify → team-fix (循环)`

| 阶段 | 代理 | 说明 |
|------|------|------|
| **team-plan** | explore + planner | 分解任务为子任务图 |
| **team-prd** | analyst + critic | 提取需求和验收标准 |
| **team-exec** | executor/designer/debugger | 并行执行子任务 |
| **team-verify** | verifier + reviewers | 验证通过后进入修复循环 |
| **team-fix** | executor/debugger | 修复缺陷后返回 exec |

### 与 Claude Code 原生团队对比

| 特性 | Team (本技能) | Claude Code 原生 /swarm |
|------|--------------|------------------------|
| **存储** | JSON in `~/.claude/teams/` | 需配置 |
| **依赖** | 无外部依赖 | better-sqlite3 (旧版) |
| **任务claiming** | Lead 预分配 | SQLite 事务 |
| **通信** | SendMessage (DM/广播) | 需手动实现 |
| **任务依赖** | 内置 blocks/blockedBy | 需手动管理 |
| **Git Worktree** | 内置隔离支持 | 需手动处理 |
| **CLI Worker** | Codex + Gemini 混合 | 不支持 |

### Team + Ralph 组合

当使用 `/team ralph` 时，Team 包装在 Ralph 的持久化循环中：

- **Team orchestration** — 多代理分阶段管道
- **Ralph persistence** — 失败重试，架构验证，迭代跟踪

### 使用示例

```bash
# 基本用法 - 3个执行者修复 TypeScript 错误
/team 3:executor "fix all TypeScript errors across the project"

# 混合团队 - 2个Codex做安全审查，1个Claude做实现
/team 3 "refactor auth module with security review"

# Ralph 持久化 - 复杂任务持续迭代直到完成
/team ralph "build a complete REST API for user management"

# 使用 Codex CLI worker 做代码审查
/team 2:codex "review architecture and suggest improvements"
```

### 阶段间 Handoff 约定

阶段转换时，之前阶段的上下文（决策、拒绝的风险）需要保存到 handoff 文件：

```markdown
## Handoff: team-plan → team-exec
- **Decided**: 微服务架构，3个服务 (auth, api, worker)。PostgreSQL 持久化，JWT 认证。
- **Rejected**: Monolith (扩展性问题), MongoDB (团队专长是 SQL)
- **Risks**: Worker 服务需要 Redis 队列 — 尚未配置
- **Files**: DESIGN.md, TEST_STRATEGY.md
- **Remaining**: 数据库迁移脚本, CI/CD 配置, Redis 配置
```

### 取消团队

```bash
使用 cancel skill  # 优雅关闭所有代理，清理状态
```

---

## 🔧 配置与管理

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **hud** | 配置HUD显示选项(布局、预设、显示元素) | 自定义界面显示 |
| **setup** | 安装/更新路由，发送到正确的OMC设置流程 | 首次设置或更新 |
| **skill** | 管理本地skills：列表、添加、删除、搜索、编辑 | skill管理 |
| **project-session-manager** | 工作树优先的开发环境管理器 | 管理issue、PR、功能分支 |

### 使用方法
```
使用 hud skill
使用 setup skill
使用 skill skill list
使用 project-session-manager skill
```

---

## 🧪 QA与验证

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **ultraqa** | QA循环：测试、验证、修复、重复 | 确保质量的功能开发 |
| **visual-verdict** | 截图与参考的结构化视觉QA判决 | UI测试、视觉回归 |
| **systematic-debugging** | 系统化调试方法论 | 遇到bug或测试失败 |
| **verification-before-completion** | 完成前验证，证据优先 | 声称完成前必须调用 |

### 使用方法
```
使用 ultraqa skill
使用 visual-verdict skill
使用 systematic-debugging skill
使用 verification-before-completion skill
```

---

## 📝 代码审查

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **requesting-code-review** | 请求代码审查 | 完成后请求审查 |
| **receiving-code-review** | 接收代码审查反馈 | 收到审查意见时 |

### 使用方法
```
使用 requesting-code-review skill
使用 receiving-code-review skill
```

---

## 🔍 研究与外部信息

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **external-context** | 并行文档专家代理，外部搜索和文档查找 | 需要参考外部资料 |
| **sciomc** | 并行科学家代理协调，综合分析 | 多角度研究分析 |
| **ask** | 路由到Claude/Codex/Gemini，捕获artifacts | 多模型协作 |

### 使用方法
```
使用 external-context skill "<搜索主题>"
使用 sciomc skill
使用 ask skill "<问题>"
```

---

## 💾 记忆与学习

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **writer-memory** | 代理记忆系统：追踪角色、关系、场景、主题 | 写作项目 |
| **learner** | 从当前对话中提取学习的skill | 积累经验到skill |

### 使用方法
```
使用 writer-memory skill
使用 learner skill
```

---

## 🛠️ 开发工具

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **writing-skills** | 创建新skill指南 | 创建自己的skill |
| **subagent-driven-development** | 子代理驱动开发 | 执行有独立任务的计划 |
| **dispatching-parallel-agents** | 并行代理分发 | 2+个独立任务并行 |

### 使用方法
```
使用 writing-skills skill
使用 subagent-driven-development skill
使用 dispatching-parallel-agents skill
```

---

## 🔀 Git工作流

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **using-git-worktrees** | Git Worktrees隔离开发 | 需要与当前工作隔离 |
| **finishing-a-development-branch** | 分支完成工作流 | 实现完成后的合并决策 |

### 使用方法
```
使用 using-git-worktrees skill
使用 finishing-a-development-branch skill
```

---

## 🎯 TDD与质量

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **test-driven-development** | 测试驱动开发 | 实现任何功能前 |
| **writing-plans** | 编写详细实现计划 | 多步骤任务 |

### 使用方法
```
使用 test-driven-development skill
使用 writing-plans skill
```

---

## 🔄 OMC生态

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **omc-setup** | 安装/刷新oh-my-claudecode | 插件、npm、本地开发设置 |
| **omc-doctor** | 诊断和修复OMC安装问题 | 遇到安装问题时 |
| **omc-reference** | OMC代理目录、工具路由、提交协议 | 代理编排时自动加载 |
| **omc-teams** | CLI团队运行时(claude/codex/gemini) | tmux中的进程并行 |
| **release** | 自动化发布工作流 | 发布新版本 |
| **cancel** | 取消活动的OMC模式 | 停止autopilot/ralph等 |
| **configure-notifications** | 配置通知(Telegram/Discord/Slack) | 设置通知集成 |
| **mcp-setup** | 配置MCP服务器 | 增强代理能力 |

### 使用方法
```
使用 omc-setup skill
使用 omc-doctor skill
使用 omc-reference skill
使用 omc-teams skill
使用 release skill
使用 cancel skill
使用 configure-notifications skill
使用 mcp-setup skill
```

---

## 🎨 专业工具

| Skill | 说明 | 使用场景 |
|-------|------|----------|
| **ai-slop-cleaner** | 清理AI生成的代码垃圾，回归安全 | 清理AI生成的低质量代码 |
| **ccg** | Claude-Codex-Gemini三模型编排 | 多模型协作 |
| **trace** | 证据驱动的追踪车道 | 并发问题因果追踪 |
| **ralplan** | 共识规划入口 | 模糊请求的门控 |

### 使用方法
```
使用 ai-slop-cleaner skill
使用 ccg skill
使用 trace skill
```

---

## OpenCode 工具Skills

| Skill | 说明 | 环境变量 |
|-------|------|----------|
| **gog** | Google Workspace CLI (Gmail, Calendar, Drive等) | 需要OAuth |
| **opentwitter** | Twitter/X API via 6551 API | TWITTER_TOKEN |
| **tiktok-automation** | TikTok自动化 (Rube MCP) | Rube MCP |
| **videodb** | 视频理解与处理 | VIDEO_DB_API_KEY |

### 使用方法
```
使用 gog skill "<命令>"
使用 opentwitter skill "<操作>"
使用 tiktok-automation skill
使用 videodb skill "<操作>"
```

---

## Claude Code Skills

| Skill | 功能 | 分类 |
|-------|------|------|
| automation | BioBlend和Planemo专家 | Galaxy |
| brainstorming | 头脑风暴 | 协作 |
| collaboration | 团队协作最佳实践 | 协作 |
| conda-recipe | Conda/Bioconda配方构建 | 生物信息 |
| data-analysis-patterns | 数据聚合模式 | 数据 |
| data-backup | 智能备份系统 | 工具 |
| data-visualization | 数据可视化最佳实践 | 数据 |
| dispatching-parallel-agents | 并行代理分发 | 协作 |
| documentation | 文档编写 | 文档 |
| documentation-organization | 文档组织 | 文档 |
| executing-plans | 执行书面计划 | 协作 |
| finishing-a-development-branch | 分支完成 | Git |
| folder-organization | 文件夹组织 | 最佳实践 |
| frontend-slides | HTML演示创建 | 工具 |
| fundamentals | 生物信息学基础(SAM/BAM) | 生物信息 |
| hackmd | HackMD集成 | 工具 |
| jupyter-notebook | Jupyter数据分析 | 数据 |
| managing-environments | 环境管理 | 最佳实践 |
| obsidian | Obsidian笔记集成 | 工具 |
| phylogenetics | 系统发育分析 | 生物信息 |
| plan-first | 计划优先 | 最佳实践 |
| project-sharing | 项目打包分享 | 协作 |
| receiving-code-review | 接收代码审查 | 协作 |
| requesting-code-review | 请求代码审查 | 协作 |
| scientific-publication | 科学出版 | 论文 |
| self-improvement | 自我改进 | 最佳实践 |
| skill-management | Skill管理 | 工具 |
| subagent-driven-development | 子代理开发 | 协作 |
| systematic-debugging | 系统化调试 | 最佳实践 |
| test-driven-development | 测试驱动开发 | 最佳实践 |
| token-efficiency | Token优化 | 最佳实践 |
| tool-wrapping | Galaxy工具包装 | Galaxy |
| using-git-worktrees | Git Worktrees使用 | Git |
| using-superpowers | Superpowers使用指南 | 入门 |
| verification-before-completion | 完成前验证 | 最佳实践 |
| vgp-pipeline | VGP基因组组装 | 生物信息 |
| workflow-development | Galaxy工作流开发 | Galaxy |
| writing-plans | 编写计划 | 协作 |
| writing-skills | 创建Skills | 工具 |

---

## 📥 安装说明

### 克隆到本地
```bash
git clone git@github.com:hzm8341/my_skills.git ~/my_skills
```

### 复制Skills到OpenCode
```bash
# Superpowers
cp -r opencode_superpowers/* ~/.config/opencode/skills/superpowers/

# 工具Skills
cp -r opencode_skills/* ~/.agents/skills/
```

### 复制Skills到Claude Code
```bash
mkdir -p .claude/skills
ln -s ~/my_skills/opencode_superpowers/* .claude/skills/
ln -s ~/my_skills/claude_code_skills/* .claude/skills/
```

### 符号链接（推荐）
```bash
# 在项目目录中
mkdir -p .claude/skills
ln -s /path/to/my_skills/opencode_superpowers/brainstorming .claude/skills/
# ... 其他skills
```

---

## 🔄 更新Skills

```bash
cd ~/my_skills
git pull origin main
```

---

## ⚠️ 核心原则

1. **使用Superpowers优先**: 如果不确定用什么，优先使用相关的Superpower
2. **先测试再部署**: 创建新Skill时，遵循TDD原则
3. **触发即调用**: 如果有1%的可能性某个skill适用，就调用它
4. **验证后断言**: 使用 verification-before-completion 确认完成

---

## 🤝 贡献

欢迎提交Issue和Pull Request来改进这个Skills集合！

---

## 📄 许可证

MIT License

---

*Last updated: 2026-03-31*
