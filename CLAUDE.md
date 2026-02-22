# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个 Claude Code 插件，用于系统化地完成 AI 短剧的文字创作工作。输出物可直接用于即梦AI等平台进行视频制作。

## 插件结构

```
ai-short-drama/
├── .claude-plugin/
│   └── plugin.json           # 插件元数据（name, version, skills, commands）
├── commands/
│   └── ai-short-drama.md     # 斜杠命令定义（/ai-short-drama）
├── skills/
│   └── ai-short-drama/
│       ├── SKILL.md          # 技能定义和触发条件
│       └── references/       # 各阶段工作流参考文档
│           ├── phase1-planning.md    # 策划阶段
│           ├── phase2-character.md   # 角色设计
│           ├── phase3-storyboard.md  # 分镜脚本
│           ├── phase4-script.md      # 配音台本
│           ├── phase5-export.md      # 导出
│           ├── story-outline.md      # 故事大纲模板
│           ├── character-card.md     # 角色设定卡模板
│           ├── storyboard.md         # 分镜脚本模板
│           └── prompt-templates.md   # 提示词模板库
└── README.md
```

## 工作流程（5 阶段）

```
策划 → 角色设计 → 分镜脚本 → 配音台本 → 导出
```

| 阶段 | 命令 | 核心输出 |
|------|------|----------|
| 策划 | `plan` | 故事大纲、项目配置 |
| 角色 | `character` | 角色设定卡 + 即梦AI图片提示词 |
| 分镜 | `storyboard` | 分镜脚本 + 视频提示词 |
| 配音 | `script` | 配音台本（台词 + 情绪标注）|
| 导出 | `export` | 全部提示词汇总包 |

## 输出文件结构

用户项目目录的标准结构：

```
/用户项目目录/
├── 00_项目配置.md          # 项目元信息和进度追踪
├── 01_故事大纲.md          # 三幕结构 + 分集大纲
├── 02_角色设定/
│   ├── 角色名_设定卡.md
│   └── 角色名_外观提示词.md
├── 03_分镜脚本/
│   └── 第X集_分镜.md
├── 04_视频提示词/
│   └── 第X集_提示词.md
├── 05_配音台本/
│   └── 第X集_配音.md
└── 99_导出包/
    ├── 全部提示词.md       # 直接复制到即梦AI
    └── 配音文本.md
```

## 提示词编写规范

### 视频提示词公式

```
[场景描述] + [主体特征与动作] + [视觉风格] + [情绪或氛围] + [镜头语言]
```

### 角色图片提示词公式

```
[人物外貌] + [服装描述] + [表情姿态] + [风格] + [光影]
```

### 示例

```
黄昏时分的城市街道，夕阳将天空染成橙红色。一位25岁的职场女性，穿着职业套装，疲惫地走在人行道上，偶尔抬头看看天，眼神中透露着孤独。温暖的橙色调，电影感构图，镜头从侧面中景跟随她缓慢移动。
```

## 扩展指南

### 添加新的工作流阶段

1. 在 `skills/ai-short-drama/references/` 创建 `phaseN-xxx.md`
2. 更新 `SKILL.md` 中的执行步骤
3. 更新 `commands/ai-short-drama.md` 的命令列表

### 添加新的提示词模板

在 `references/prompt-templates.md` 中按场景类型添加模板，遵循现有结构：

- 场景模板
- 角色动作模板
- 运镜模板
- 风格模板

## 与即梦AI的配合流程

1. **图片生成**：复制角色外观提示词 → 即梦AI生成角色参考图
2. **视频生成**：复制视频提示词 + 参考图 → 即梦AI生成视频片段
3. **配音**：复制配音台本 → 即梦AI配音
4. **后期**：剪辑软件整合成片
