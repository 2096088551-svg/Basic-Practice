# 基础实践作业仓库

## 目录

- [梗概](#梗概)
- [第一次作业](#第一次作业)
- [第二次作业](#第二次作业)

## 梗概

**基础实践**是用于存放基础实践课程作业的仓库。本仓库收纳课程中的独立作业项目，每个子目录对应一次实践任务。

## 第一次作业

- [AIGC 在游戏音频设计中的应用调研](Homework%201/Homework%201.md)

## 第二次作业

### 晴天傍晚校园操场环境声设计

![校园操场场景](Homework%202/Final/Images/操场01.jpg)

### 项目简介

本项目以晴天傍晚的校园操场为环境声设计对象。声音由持续存在的操场环境底噪、风声和树叶声，以及随机出现的跑步、走路和远处聊天声组成。

最终音频资产统一采用：

- 采样率：48 kHz
- 位深：24bit
- 声道：stereo
- 格式：wav

### 快速查看

| 内容 | 路径 |
|---|---|
| Wwise 工程 | [CampusPlaygroundAudio](Homework%202/Final/WwiseProject/CampusPlaygroundAudio/CampusPlaygroundAudio.wproj) |
| 最终音频资产 | [Edited](Homework%202/Final/Edited/) |
| 场景图片 | [Images](Homework%202/Final/Images/) |
| 配置与测试截图 | [Evidence](Homework%202/Final/Evidence/) |
| 录音与制作说明 | [Preparation.md](Homework%202/Preparation.md) |

### 场景说明

傍晚的校园操场，跑道上零星分布着跑步和散步的人，足球场上有人在活动，场边树叶被风吹动。远处有模糊的聊天和欢笑声，整体保持校园傍晚的生活感，但不突出某一个人的具体对话。

### 声音结构

| 类型 | 内容 | Wwise 实现 |
|---|---|---|
| 持续基底声 | 操场环境、风声、树叶声和远处活动声 | Infinite Loop |
| 跑步随机声 | 跑步经过和脚步 | Run_Random |
| 走路随机声 | 走路经过和脚步 | Walk_Random |
| 聊天随机声 | 远处模糊聊天 | Chat_Random |
| 阵风随机声 | 风声片段 | Wind_Random |
| 风吹树叶随机声 | 风吹树叶的沙沙声 | Leaves_Random |

### Wwise 工程结构

```text
Audio
  Containers
    Playground
      Ambience
        Playground_Base_Loop
      RandomEvents
        Run_Random
        Walk_Random
        Chat_Random
        Wind_Random
        Leaves_Random
```

主要配置：

- 工程名称：CampusPlaygroundAudio
- Wwise 版本：2025.1.11.9262
- 基底声：Infinite Loop
- 随机容器：step
- 随机声：3D Spatialization
- 距离衰减：Attenuation_Playground
- 最大衰减距离：50 米

### 如何试听

1. 使用 Wwise 2025.1.11.9262 打开根目录中的 Wwise 工程。
2. 打开“Sessions > Soundcaster Sessions > Scene_Playground_Test".
3. 点击"Play_Playground_Base".
4. 多次点击"Play_Run_Random"、"Play_Walk_Random"等事件
5. 点击Stop_Playground_Base停止基底声.

### 文件结构

```text
Homework 2/
  Preparation.md
  Final/
    Edited/        最终声音资产
    WwiseProject/  Wwise 工程
    Images/        场景图片
    Evidence/      Wwise 配置与测试截图
    Raw/           原始录音与筛选素材
```
