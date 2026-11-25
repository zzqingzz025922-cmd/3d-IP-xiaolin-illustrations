# 小林 · 3D 黏土配图

> 用小林 IP，把文章里的判断、流程和情绪，变成一张能看懂的 3D 黏土配图。

**白底柔光 · 固定角色 · 概念隐喻 · 可换装 · 支持局部编辑**

这是一个供 Codex 使用的 Skill，包含角色设定、参考图片、构图方法、生图 prompt 和验收规则。它指导具有图像生成能力的环境完成配图，生成与编辑依赖环境提供的内置 `image_gen` 工具。

![小林「灵感枯竭」配图：穿白衬衫和深蓝马甲的小林，挤出最后一点灯泡形灵感](xiaolin-clay-illustrations%203/clay-character-illustrations/assets/examples/12-approved-clay-style.png)

上图是已确认的画风样例。后续图片参考它的材质、光照、明度与饱和度，服装、动作和道具随主题变化。

## 可以用来做什么

| 任务 | 产出 |
|---|---|
| 文章、帖子、博客配图 | 选择值得视觉化的段落，生成正文插图 |
| 抽象观点与情绪表达 | 用角色动作和物件表达信息过载、灵感枯竭、信任建立等概念 |
| 配图规划 | 给出位置、核心意思、小林动作、必要物件和可选短标注 |
| 角色换装 | 替换服装，尽量保持五官、比例、表情和构图 |
| 局部修改 | 调整指定内容，如颜色、道具或服装，并明确其他保留项 |

默认生成 16:9 横版、纯白背景、柔和光照的 3D 黏土潮玩风格图片。每张图只表达一个核心意思，角色参与动作，避免堆满信息。比例、背景与文字可按本次需求调整。

## 快速安装

### 1. 获取仓库

在终端执行：

```bash
git clone https://github.com/zzqingzz025922-cmd/3d-IP-xiaolin-illustrations.git
cd 3d-IP-xiaolin-illustrations
```

### 2. 安装技能（macOS / Linux）

以下命令从仓库根目录执行，使用当前实际上传路径。目录名中的空格已用引号处理。

```bash
xiaolin_skill_source="./xiaolin-clay-illustrations 3/clay-character-illustrations"
xiaolin_skill_target="${CODEX_HOME:-$HOME/.codex}/skills/clay-character-illustrations"

if [ -e "$xiaolin_skill_target" ]; then
  printf '%s\n' '检测到同名技能，未覆盖。请先备份并移出旧目录，再重新安装。'
else
  mkdir -p "$(dirname "$xiaolin_skill_target")"
  cp -R "$xiaolin_skill_source" "$xiaolin_skill_target"
fi
```

需要安装的是内层 `clay-character-illustrations` 文件夹，`SKILL.md` 应直接位于该文件夹内。仓库名称是 `3d-IP-xiaolin-illustrations`，技能调用名称保持为 **`$clay-character-illustrations`**。

也可以在 GitHub 使用 **Code → Download ZIP**，解压后进入仓库根目录，再执行上述安装命令。该方式不需要执行 `git clone` 和随后的 `cd` 命令。仓库根目录另附制作时的 [独立安装包](xiaolin-clay-illustrations-upload.zip?raw=true)，其内部文件夹结构与仓库略有不同，安装时同样选取内层 `clay-character-illustrations`。

无需安装原版小黑 Skill。本仓库不包含独立生图脚本；如果运行环境没有图像工具，可以规划配图和编写 prompt，不能直接产出图片。

## 使用示例

### 生成一张配图

```text
Use $clay-character-illustrations 用小林为“灵感枯竭”生成一张配图。
```

### 指定服装和场景

```text
Use $clay-character-illustrations 用小林表现“信息过载”。
穿白衬衫、深蓝针织马甲和黑裙，正在被一堆信息方块压住。
16:9 横版、白底柔光，颜色与技能内的小林参考图一致。
```

### 先规划，不生成

```text
Use $clay-character-illustrations 先不要生图。
为下面的文章规划 4 张正文配图，说明放置位置、核心意思、
小林在做什么、需要哪些道具，以及是否需要短标注。

【在这里粘贴文章】
```

### 换装，保留画面

附上或明确指定待修改图片，再输入：

```text
Use $clay-character-illustrations 把这张图里的小林换成
白衬衫、深蓝针织马甲和黑裙，保留人物表情、动作、道具、构图和白底。
```

### 调整颜色

```text
Use $clay-character-illustrations 适度提高这张图的明度和饱和度，
保留自然肤色、深色头发层次、人物动作、道具与构图，避免高光过曝。
```

## 小林如何保持可识别

默认识别短语：**齐刘海红圈高马尾女生**。

小林的关键外形包括：大头小身体、圆润脸颊、深棕眼睛、浓密上睫毛、厚齐刘海、近黑深棕头发、粉色眼妆、桃色皮肤、细雀斑和银色圈耳环。高位波浪马尾与红发圈是默认造型；披发和帽子可使用已提供的变体。

| 分级 | 控制什么 | 使用方式 |
|---|---|---|
| P0 核心身份 | 脸型、五官、齐刘海、发色、肤色、面部标记和比例 | 普通换装、换动作时保持 |
| P1 标志造型 | 默认高马尾、红发圈、圈耳环 | 可按用户要求或已认可变体调整 |
| P2 场景变量 | 服装、表情、动作、视线和道具 | 按每次主题设置 |
| S 画风 | 材质、光照、色彩与背景 | 独立于角色身份和服装 |

这些分级是本技能的维护规则，不是模型数值权重。角色名称与识别短语用于描述和检索，不能代替图像参考。完整结构见 [关键词与中文标准模板](xiaolin-clay-illustrations%203/clay-character-illustrations/references/ip-keywords.md)。

## 内置的 12 张参考图

| 编号 | 图片内容 | 主要作用 |
|---|---|---|
| 01 | 高兴、悲伤、生气、惊讶表情图 | 五官与情绪参考 |
| 02 | 白衬衫、深蓝马甲、黑裙通勤装 | 通勤造型 |
| 03 | 基础装正面、侧面、背面三视图 | 默认身份与比例主参考 |
| 04 | 工作主题海报 | 相关动态、材质与道具配色 |
| 05 | 咖啡主题海报 | 暖橙与蓝色关系、立体道具质感 |
| 06 | 健身主题海报 | 青蓝与紫色关系、立体道具质感 |
| 07 | 针织帽、背心、宽松牛仔裤 | 街头造型 |
| 08 | 粉色上衣、格纹衬衫系腰、牛仔长裤 | 休闲造型 |
| 09 | 披发、红色套装与白绳花饰 | 红色造型变体 |
| 10 | 猫耳帽、墨镜、黑白搭配 | 黑白造型变体 |
| 11 | 猫帽、蓝绿条纹套装、猫拖鞋 | 居家造型 |
| 12 | 白底“灵感枯竭”换装成图 | 用户确认的画风主参考 |

默认使用 03 锁定身份、12 校准画风，按需增加表情或服装图，通常每次选择 1–3 张必要参考。海报中的文字、品牌标志、背景、编辑选框和版式不作为默认生成要求。

图片文件及其边界见 [参考图索引](xiaolin-clay-illustrations%203/clay-character-illustrations/references/reference-index.md)。这些图片按用途保存，不需要凑成固定的 8 张，也不需要与原版的 8 张展示样例一一对应。

## 目录结构

```text
3d-IP-xiaolin-illustrations/
├── README.md
├── xiaolin-clay-illustrations-upload.zip
└── xiaolin-clay-illustrations 3/
    ├── README.md
    ├── LICENSE
    └── clay-character-illustrations/
        ├── SKILL.md
        ├── LICENSE
        ├── NOTICE.md
        ├── agents/openai.yaml
        ├── references/          角色、画风、模板、构图和验收规则
        └── assets/
            ├── character/      8 张角色、表情与造型图
            └── examples/       3 张海报参考 + 1 张已确认画风图
```

## 如何替换或补充参考图

所有修改都在技能文件夹内进行，改完后同步到实际安装目录。修改仓库不会自动更新已安装的副本。

| 想改什么 | 更新哪些内容 |
|---|---|
| 角色身份 | 03 三视图、01 表情图，以及角色定义、关键词、prompt 和验收规则 |
| 某套衣服 | 对应服装图及参考图索引中的描述 |
| 默认画风、明度和饱和度 | 12 画风图、画风定义及相关 prompt、验收规则 |
| 新增造型或样例 | 保存新图，在参考图索引中注明用途和不应复制的内容 |

保持文件名可减少路径修改；若更换文件名，要同步所有引用。仅把图片放进文件夹不会自动让模型使用它，需要在技能中规定读取并传入图像工具。

主要维护入口：[技能正文](xiaolin-clay-illustrations%203/clay-character-illustrations/SKILL.md)、[角色定义](xiaolin-clay-illustrations%203/clay-character-illustrations/references/character-ip.md)、[画风定义](xiaolin-clay-illustrations%203/clay-character-illustrations/references/style-dna.md)、[生图与编辑模板](xiaolin-clay-illustrations%203/clay-character-illustrations/references/prompt-template.md)、[验收清单](xiaolin-clay-illustrations%203/clay-character-illustrations/references/qa-checklist.md)。

## 验证与使用边界

制作过程中已实际生成“灵感枯竭”配图并完成通勤换装，上方展示的是已确认画风的结果。技能文件格式、图片完整性、引用路径与调用配置已检查；后续整理的标准模板尚未重新进行完整生图回归。

角色一致性依赖参考图和具体生成结果，复杂姿势、不同角度或连续多张图仍可能出现细节漂移。生成后应检查五官、手指、服装、道具接触、裁切和文字；局部编辑也可能产生细微变化。

## 来源与许可

文字工作流改编自 [Ian 的 ian-xiaohei-illustrations](https://github.com/helloianneo/ian-xiaohei-illustrations)，保留原项目的 [MIT License](xiaolin-clay-illustrations%203/LICENSE) 与 [来源说明](xiaolin-clay-illustrations%203/clay-character-illustrations/NOTICE.md)。

小林名称与原始参考图由用户提供。文本工作流的 MIT License 不自动授予参考图片、其中品牌或其他素材的权利；图片来源与使用说明见 NOTICE。
