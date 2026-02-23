---
description: 提示词生成器 - 生成、优化、转换 Seedance 2.0 视频提示词
argument-hint: [场景描述] --mode [standard|phased|continuous] --style [风格]
allowed-tools: [Read, Write, Edit, Glob, Grep]
---

# 提示词生成器

为 Seedance 2.0 生成高质量视频提示词。

## 用法

```bash
# 基础用法
/drama-prompt [场景描述]

# 指定模式
/drama-prompt [场景描述] --mode [standard|phased|continuous]

# 指定风格
/drama-prompt [场景描述] --style [realistic|cinematic|anime|fantasy]

# 优化现有提示词
/drama-prompt --optimize [现有提示词]
```

## 参数说明

| 参数 | 说明 | 默认值 |
|------|------|--------|
| `[场景描述]` | 简要描述你想要生成的场景 | - |
| `--mode` | 提示词模式 | standard |
| `--style` | 视觉风格 | realistic |
| `--optimize` | 优化现有提示词 | - |
| `--duration` | 视频时长（秒） | 6 |
| `--voice` | 是否包含配音 | false |

### 模式说明

| 模式 | 说明 | 适用场景 |
|------|------|----------|
| `standard` | 标准模式，每个镜头独立 | 对话、日常、情感 |
| `phased` | 时间分段模式，15秒内精确控制 | 穿越、变身、动作爆发 |
| `continuous` | 单镜头模式，一镜到底 | 追逐、跑酷、长镜头 |

### 风格说明

| 风格 | 说明 |
|------|------|
| `realistic` | 现实主义，自然光线，写实色彩 |
| `cinematic` | 电影质感，戏剧光影，高对比 |
| `anime` | 动漫风格，鲜艳色彩，夸张表现 |
| `fantasy` | 奇幻风格，梦幻光影，特效丰富 |
| `scifi` | 科幻风格，霓虹灯光，未来感 |
| `noir` | 黑色电影，高对比，阴影深沉 |

## 执行流程

### Step 1: 分析需求

1. 解析用户输入的场景描述
2. 确定提示词模式（默认 standard）
3. 确定视觉风格（默认 realistic）
4. 确定是否需要配音

### Step 2: 生成提示词

根据模式生成对应格式的提示词：

**标准模式**：
```
Subject: [主体描述]
Action: [动作描述]
Camera: [运镜描述]
Style: [风格描述]
Constraints: [约束条件]
```

**时间分段模式**：
```
15秒，[整体风格]

[时间段1]：[画面+动作+镜头]
[时间段2]：[画面+动作+镜头]
[时间段3]：[画面+动作+镜头]

音效：[音频描述]
限制：[负面提示]
```

**单镜头模式**：
```
Single continuous shot, [主体描述],
[动作轨迹描述],
camera [镜头运动],
final reveal [最终揭示]
```

### Step 3: 质量检查

- [ ] 主体是否明确
- [ ] 动作是否具体
- [ ] 镜头是否清晰
- [ ] 风格是否一致
- [ ] 时长是否合理

### Step 4: 输出结果

生成可直接复制使用的提示词。

## 示例

### 示例1：标准模式

```
输入：
/drama-prompt 女孩在黄昏的街道上行走，表情孤独

输出：
Subject: 25岁职场女性，穿着职业套装，背着公文包
Action: 疲惫地走在黄昏的街道上，偶尔抬头看看天，眼神透露着孤独
Camera: 中景，侧面跟随，缓慢移动
Style: 电影感，温暖橙色调，柔和光线
Constraints: 无模糊，6秒时长
```

### 示例2：时间分段模式

```
输入：
/drama-prompt 女孩穿越到古代 --mode phased

输出：
15秒，中国古装短剧风格，电影画质

0-3秒：现代都市夜景，一位身穿白色连衣裙的年轻女孩站在天桥上低头看手机，突然脚下一滑
镜头：中景，平视，轻微晃动

3-8秒：女孩失重坠落，身体在空中旋转，周围景物扭曲变形，光线拖尾
镜头：环绕跟随，快速旋转，光影流动

8-15秒：画面骤然稳定，女孩落在古代宫殿的花园中，周围樱花飞舞
镜头：仰拍全景推进至中景

音效：都市车流声 → 坠落风声 → 古琴轻响
限制：无模糊，人物面部清晰
```

### 示例3：单镜头模式

```
输入：
/drama-prompt 摩托车穿越地中海村庄追逐 --mode continuous

输出：
Single continuous shot, motorcycle chase through narrow streets of a Mediterranean village,

camera weaves through hanging laundry and market stalls,
rider barely dodges obstacles,

final reveal opens to massive cliff edge overlooking infinite ocean at golden hour

风格：action thriller, warm tones, cinematic
限制：15秒
```

### 示例4：优化提示词

```
输入：
/drama-prompt --optimize "一个人在跑步"

输出：
Subject: 30岁男性跑者，穿着蓝色运动背心和黑色短裤，额头有汗水
Action: 在公园跑道上中等速度奔跑，呼吸有节奏，偶尔擦汗
Camera: 侧面中景跟随，保持稳定距离
Style: 健康活力，自然光线，写实风格
Constraints: 无模糊，动作流畅，6秒时长

优化建议：
1. 增加具体的人物描述（年龄、穿着）
2. 明确跑步的场景和速度
3. 添加运镜描述
4. 确定风格和时长
```

## 交互模式

如果不提供参数，进入交互模式：

```
🎬 Seedance 2.0 提示词生成器

请描述你想生成的场景：
> [用户输入场景描述]

选择提示词模式：
1. 标准模式（推荐新手）
2. 时间分段模式（适合连贯动作）
3. 单镜头模式（适合追逐场景）
> [用户选择]

选择视觉风格：
1. 现实主义
2. 电影质感
3. 动漫风格
4. 奇幻风格
5. 科幻风格
> [用户选择]

是否需要配音？
> [是/否]

---

生成提示词：
[生成的提示词]
```

## 参考资源

详细模板请查阅：
- `skills/seedance-prompts/references/prompt-templates.md` - 完整提示词模板库
- `skills/seedance-prompts/references/camera-movements.md` - 运镜参考
- `skills/seedance-prompts/references/scene-types.md` - 场景类型详解
