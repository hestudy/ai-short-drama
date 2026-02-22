# AI 短剧文字工作流

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Claude Code Plugin - 在 Claude Code 中完成 AI 短剧的全部文字创作工作

## 简介

这是一个 Claude Code 插件，用于系统化地完成 AI 短剧的文字创作工作。生成的提示词和台本可直接用于即梦AI等平台进行视频制作。

## 安装

### 方式一：克隆到用户级目录

```bash
cd ~/.claude/plugins
git clone https://github.com/hestudy/ai-short-drama.git
```

### 方式二：克隆到项目级目录

```bash
mkdir -p your-project/.claude/plugins
cd your-project/.claude/plugins
git clone https://github.com/hestudy/ai-short-drama.git
```

## 使用方法

### 命令方式

```
/ai-short-drama new "剧名" --episodes 10
/ai-short-drama plan              # 策划阶段
/ai-short-drama character         # 角色设计
/ai-short-drama storyboard        # 分镜脚本
/ai-short-drama script            # 配音台本
/ai-short-drama export            # 导出提示词
```

### 自然语言触发

直接说：
- "我想创作一个AI短剧"
- "帮我写短剧"
- "生成短剧提示词"

## 工作流程

```
┌─────────────────────────────────────────────────────────────┐
│                    Claude Code 文字工作流                    │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  阶段一        阶段二        阶段三        阶段四        阶段五│
│  ┌─────┐     ┌─────┐     ┌─────┐     ┌─────┐     ┌─────┐   │
│  │策划 │ ──▶ │角色 │ ──▶ │分镜 │ ──▶ │配音 │ ──▶ │导出 │   │
│  │     │     │设计 │     │脚本 │     │台本 │     │     │   │
│  └─────┘     └─────┘     └─────┘     └─────┘     └─────┘   │
│     │           │           │           │           │      │
│     ▼           ▼           ▼           ▼           ▼      │
│  故事大纲    角色设定卡    分镜脚本    配音台本    提示词包  │
│              角色提示词    视频提示词              配音文本  │
│                                                            │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
                    ┌─────────────────┐
                    │ 复制到即梦AI    │
                    │ 进行视频制作    │
                    └─────────────────┘
```

## 输出物清单

| 输出物 | 说明 | 复制到即梦AI |
|--------|------|--------------|
| 故事大纲 | 完整的故事框架 | 规划参考 |
| 角色设定卡 | 角色信息 + 外观提示词 | ✅ 图片生成 |
| 分镜脚本 | 详细的镜头拆解 | 制作指导 |
| 视频提示词 | 每个镜头的即梦AI提示词 | ✅ 视频生成 |
| 配音台本 | 角色台词 + 情绪标注 | ✅ AI配音 |
| 制作清单 | 制作进度跟踪 | 项目管理 |

## 插件结构

```
ai-short-drama/
├── .claude-plugin/
│   └── plugin.json           # 插件元数据
├── commands/
│   └── ai-short-drama.md     # 斜杠命令
├── skills/
│   └── ai-short-drama/
│       ├── SKILL.md          # 技能定义
│       └── references/       # 参考文档
│           ├── story-outline.md
│           ├── character-card.md
│           ├── storyboard.md
│           ├── prompt-templates.md
│           └── phase*.md
└── README.md
```

## 提示词示例

### 视频生成提示词结构
```
[场景描述] + [主体特征与动作] + [视觉风格] + [情绪或氛围] + [镜头语言]
```

### 示例
```
黄昏时分的城市街道，夕阳将天空染成橙红色。一位25岁的职场女性，穿着职业套装，疲惫地走在人行道上，偶尔抬头看看天，眼神中透露着孤独。温暖的橙色调，电影感构图，镜头从侧面中景跟随她缓慢移动。
```

## 与即梦AI的配合

1. **在 Claude Code 中**：完成所有文字创作
2. **导出提示词**：复制生成的提示词和台本
3. **在即梦AI中**：
   - 角色外观提示词 → 生成角色参考图
   - 场景提示词 → 生成场景参考图
   - 视频提示词 + 参考图 → 生成视频片段
   - 配音台本 → AI配音
4. **后期整合**：在剪辑软件中完成最终成片

## 许可证

[MIT License](LICENSE)

## 贡献

欢迎提交 Issue 和 Pull Request！
