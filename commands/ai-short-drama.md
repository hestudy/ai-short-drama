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
/ai-short-drama fill-prompts      # 补充缺失的提示词 ⭐ 新增
/ai-short-drama review            # 分镜审核
/ai-short-drama script            # 配音台本
/ai-short-drama export            # 导出提示词
```

## 阶段说明

| 阶段 | 命令 | 产出 |
|------|------|------|
| 策划 | plan | 故事大纲 |
| 角色 | character | 角色设定卡 + 外观提示词 |
| 分镜 | storyboard | 分镜脚本 + 视频提示词 |
| 补充 | fill-prompts | 补充缺失的提示词 ⭐ 新增 |
| 审核 | review | 审核报告 + 修正后的提示词 |
| 配音 | script | 配音台本 |
| 导出 | export | 全部提示词汇总 |

## fill-prompts 命令详解

专门用于检查和补充分镜中缺失的AI提示词。

### 执行流程

1. **扫描分镜文件**：读取所有分镜脚本
2. **识别缺失项**：找出没有提示词或提示词不完整的镜头
3. **生成缺失报告**：列出需要补充的镜头清单
4. **逐个补充**：根据分镜描述生成对应的提示词
5. **更新文件**：将补充的提示词写入分镜文件

### 输出示例

```markdown
# 提示词补充报告

## 扫描结果
- 扫描文件数：3 集
- 总镜头数：45 个
- 缺失提示词：5 个

## 需补充清单
| 集数 | 镜头 | 原因 |
|------|------|------|
| 第1集 | S01_C05 | 提示词为空 |
| 第2集 | S02_C03 | 缺少运镜描述 |
| 第2集 | S02_C08 | 提示词为空 |
| 第3集 | S03_C01 | 提示词过短 |
| 第3集 | S03_C11 | 提示词为空 |

## 补充完成
✅ 已为 5 个镜头补充提示词
```

### 使用场景

- 分镜生成后发现部分镜头缺少提示词
- 导出前进行完整性检查
- 审核前确保所有提示词完整

## 示例

```
/ai-short-drama new "时空快递员" --episodes 10
/ai-short-drama plan
/ai-short-drama storyboard
/ai-short-drama fill-prompts      # 检查并补充缺失提示词
/ai-short-drama review
/ai-short-drama export
```

## 工作流

按照以下顺序执行：

1. **策划阶段**：生成故事大纲，确定核心概念和剧情走向
2. **角色设计**：创建角色卡，生成即梦AI外观提示词
3. **分镜脚本**：拆解每集为具体镜头，生成视频提示词
4. **补充提示词**：检查并补充缺失的提示词（可选但推荐）
5. **分镜审核**：审核分镜与提示词一致性
6. **配音台本**：生成配音文本，标注情绪和语速
7. **导出**：打包所有可直接使用的内容

输出物可直接复制到即梦AI使用。
