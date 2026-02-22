---
description: AI短剧文字工作流 - 完成策划、角色、分镜、提示词、配音台本创作
argument-hint: [phase] [options]
allowed-tools: [Read, Write, Edit, Glob, Grep, Bash]
---

# AI短剧文字工作流

启动AI短剧文字创作工作流。

## 用法

```
/ai-short-drama new [剧名] --episodes [集数]
/ai-short-drama plan              # 策划阶段
/ai-short-drama character         # 角色设计
/ai-short-drama storyboard        # 分镜脚本
/ai-short-drama script            # 配音台本
/ai-short-drama export            # 导出提示词
```

## 阶段说明

| 阶段 | 命令 | 产出 |
|------|------|------|
| 策划 | plan | 故事大纲 |
| 角色 | character | 角色设定卡 + 外观提示词 |
| 分镜 | storyboard | 分镜脚本 + 视频提示词 |
| 配音 | script | 配音台本 |
| 导出 | export | 全部提示词汇总 |

## 示例

```
/ai-short-drama new "时空快递员" --episodes 10
/ai-short-drama plan
/ai-short-drama export
```

## 工作流

按照以下顺序执行：

1. **策划阶段**：生成故事大纲，确定核心概念和剧情走向
2. **角色设计**：创建角色卡，生成即梦AI外观提示词
3. **分镜脚本**：拆解每集为具体镜头，生成视频提示词
4. **配音台本**：生成配音文本，标注情绪和语速
5. **导出**：打包所有可直接使用的内容

输出物可直接复制到即梦AI使用。
