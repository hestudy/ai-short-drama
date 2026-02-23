---
name: ai-short-drama
description: This skill should be used when the user asks to "create AI short drama", "write short drama", "generate video prompts", "即梦短剧", "AI短剧", "写短剧", "生成提示词", "短剧剧本", or discusses short video drama production workflow. Provides complete workflow from planning to export for AI-generated short dramas.
version: 1.1.0
license: MIT
---

# AI短剧文字工作流

在 Claude Code 中完成 AI 短剧的全部文字创作工作，输出可直接用于即梦AI等平台的文本内容。

## 触发条件

当用户说以下内容时激活：
- "AI短剧"、"写短剧"、"短剧创作"
- "生成短剧提示词"、"即梦短剧"
- "帮我写剧本"、"视频提示词"
- 讨论短剧制作相关话题

## 命令列表

所有命令都是独立的斜杠命令：

| 命令 | 说明 |
|------|------|
| `/drama-new` | 创建新项目 |
| `/drama-plan` | 策划故事大纲 |
| `/drama-character` | 设计角色 + 生成外观提示词 |
| `/drama-storyboard` | 生成分镜脚本 + 视频提示词 |
| `/drama-fill-prompts` | 检查并补充缺失的提示词 |
| `/drama-review` | 审核分镜与提示词一致性 |
| `/drama-script` | 生成配音台本 |
| `/drama-export` | 导出全部提示词包 |

## 工作流程

```
/drama-new → /drama-plan → /drama-character → /drama-storyboard
                                                      ↓
/drama-export ← /drama-script ← /drama-review ← /drama-fill-prompts
```

## 执行步骤

### 阶段一：策划 (`/drama-plan`)
1. 收集需求（剧名、类型、集数、受众）
2. 生成故事大纲
3. 确定视觉风格

**输出**: `01_故事大纲.md`

### 阶段二：角色设计 (`/drama-character`)
1. 确认角色清单
2. 创建角色设定卡
3. 生成即梦AI图片提示词

**输出**: `02_角色设定/` + 角色外观提示词

### 阶段三：分镜脚本 (`/drama-storyboard`)
1. 确定分镜策略
2. 逐集拆分镜头
3. 为每个镜头生成即梦AI视频提示词

**输出**: `03_分镜脚本/` + `04_视频提示词/`

### 阶段三·补：补充提示词 (`/drama-fill-prompts`)
1. 扫描所有分镜文件
2. 识别缺失/异常的提示词
3. 根据分镜描述补充提示词
4. 生成补充报告

### 阶段三·五：分镜审核 (`/drama-review`)
1. 提示词完整性检查（优先）
2. 逐镜头对比分镜与提示词的一致性
3. 检查场景、角色、动作、情绪、运镜是否匹配
4. 修正不一致项
5. 生成审核报告

**检查维度**：完整性、内容一致性、技术规范性、连贯性

### 阶段四：配音台本 (`/drama-script`)
1. 确认配音风格
2. 生成配音台本

**输出**: `05_配音台本/`

### 阶段五：导出 (`/drama-export`)
1. 汇总所有提示词
2. 生成制作清单

**输出**: `99_导出包/`

## 提示词规范

### 视频提示词结构
```
[场景描述] + [主体特征与动作] + [视觉风格] + [情绪或氛围] + [镜头语言]
```

### 角色图片提示词结构
```
[人物外貌] + [服装描述] + [表情姿态] + [风格] + [光影]
```

## 输出文件结构

```
/项目目录/
├── 00_项目配置.md
├── 01_故事大纲.md
├── 02_角色设定/
├── 03_分镜脚本/
├── 04_视频提示词/
├── 05_配音台本/
└── 99_导出包/
    ├── 全部提示词.md    # 复制到即梦AI
    └── 配音文本.md
```

## 与即梦AI配合

1. 复制角色提示词 → 即梦AI生成参考图
2. 复制视频提示词 → 即梦AI生成视频
3. 复制配音台本 → 即梦AI配音
4. 剪辑软件整合

## 参考资源

详细模板和工作流请参阅 `references/` 目录：
- `story-outline.md` - 故事大纲模板
- `character-card.md` - 角色设定卡模板
- `storyboard.md` - 分镜脚本模板
- `prompt-templates.md` - 提示词模板库（含 Seedance 2.0 模板）
- `phase1-planning.md` ~ `phase5-export.md` - 各阶段工作流
- `phase3-fill-prompts.md` - 补充缺失提示词工作流 ⭐ 新增
- `phase3.5-review.md` - 分镜与提示词审核工作流
