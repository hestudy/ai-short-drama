---
description: 创建新的AI短剧项目，初始化项目配置文件
argument-hint: [剧名] --episodes [集数] --type [类型]
allowed-tools: [Read, Write, Edit, Glob, Grep, Bash]
---

# 创建新短剧项目

初始化一个AI短剧项目，创建项目配置文件和目录结构。

## 用法

```
/drama-new [剧名]
/drama-new [剧名] --episodes [集数]
/drama-new [剧名] --episodes [集数] --type [类型]
```

## 参数说明

| 参数 | 说明 | 示例 |
|------|------|------|
| 剧名 | 短剧标题 | "时空快递员" |
| --episodes | 集数（默认5集） | --episodes 10 |
| --type | 类型标签 | --type 都市言情 |

## 执行流程

1. 确认项目位置（当前目录或新建目录）
2. 创建标准目录结构：
   ```
   /项目目录/
   ├── 00_项目配置.md
   ├── 01_故事大纲.md
   ├── 02_角色设定/
   ├── 03_分镜脚本/
   ├── 04_视频提示词/
   ├── 05_配音台本/
   └── 99_导出包/
   ```
3. 生成项目配置文件 `00_项目配置.md`
4. 询问基本创作需求（类型、受众、风格偏好）

## 示例

```
/drama-new "霸道总裁爱上我" --episodes 20 --type 都市言情
/drama-new "穿越之逆袭人生" --episodes 15
/drama-new "重生之商业帝国"
```

## 下一步

项目创建后，使用 `/drama-plan` 开始策划阶段。
