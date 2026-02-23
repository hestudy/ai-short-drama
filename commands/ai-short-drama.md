---
description: AI短剧工作流概览 - 显示完整命令列表和工作流程说明
argument-hint:
allowed-tools: [Read, Write, Edit, Glob, Grep, Bash]
---

# AI短剧工作流概览

显示完整的命令列表和工作流程说明。

## 快速开始

```
/drama-new "我的短剧" --episodes 5    # 创建项目
/drama-plan                           # 策划故事
/drama-character                      # 设计角色
/drama-storyboard --all               # 生成全部分镜
/drama-fill-prompts                   # 补充缺失提示词
/drama-review --fix                   # 审核并修正
/drama-script --all                   # 生成配音台本
/drama-export                         # 导出提示词
```

## 命令列表

| 命令 | 说明 | 用法 |
|------|------|------|
| `/drama-new` | 创建新项目 | `/drama-new [剧名] --episodes [集数]` |
| `/drama-plan` | 策划故事大纲 | `/drama-plan` |
| `/drama-character` | 设计角色 | `/drama-character [--all]` |
| `/drama-storyboard` | 生成分镜脚本 | `/drama-storyboard [集数或范围]` |
| `/drama-fill-prompts` | 补充缺失提示词 | `/drama-fill-prompts` |
| `/drama-review` | 审核分镜与提示词 | `/drama-review [--fix]` |
| `/drama-script` | 生成配音台本 | `/drama-script [集数或范围]` |
| `/drama-export` | 导出提示词包 | `/drama-export` |

## 工作流程

```
┌──────────┐   ┌──────────┐   ┌───────────┐   ┌───────────────┐
│ drama-new │ → │drama-plan│ → │drama-char │ → │drama-storyboard│
└──────────┘   └──────────┘   └───────────┘   └───────┬───────┘
                                                      │
      ┌───────────────────────────────────────────────┘
      ↓
┌─────────────────┐   ┌─────────────┐   ┌──────────────┐   ┌──────────────┐
│drama-fill-prompts│ → │drama-review │ → │drama-script  │ → │drama-export  │
└─────────────────┘   └─────────────┘   └──────────────┘   └──────────────┘
```

## 各阶段产出

| 阶段 | 命令 | 核心产出 |
|------|------|----------|
| 创建 | `/drama-new` | 项目目录结构 + 配置文件 |
| 策划 | `/drama-plan` | `01_故事大纲.md` |
| 角色 | `/drama-character` | `02_角色设定/` + 外观提示词 |
| 分镜 | `/drama-storyboard` | `03_分镜脚本/` + `04_视频提示词/` |
| 补充 | `/drama-fill-prompts` | 补充报告 + 完整提示词 |
| 审核 | `/drama-review` | 审核报告 + 修正后的提示词 |
| 配音 | `/drama-script` | `05_配音台本/` |
| 导出 | `/drama-export` | `99_导出包/` |

## 提示词规范

### 视频提示词公式
```
[场景描述] + [主体特征与动作] + [视觉风格] + [情绪或氛围] + [镜头语言]
```

### 角色图片提示词公式
```
[人物外貌] + [服装描述] + [表情姿态] + [风格] + [光影]
```

## 更多帮助

- 输入 `/drama-new` 开始创建你的第一个短剧项目
- 每个命令都支持 `--help` 查看详细用法
