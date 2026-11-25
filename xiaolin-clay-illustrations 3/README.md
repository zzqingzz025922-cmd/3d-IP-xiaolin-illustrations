# 小林 · 3D 黏土配图

基于小林 IP 的 Codex Skill，用角色动作和少量物件解释文章中的判断、流程与状态。默认白底、柔光、3D 黏土潮玩质感，支持配图规划、单图生成、换装和局部编辑。

![小林配图示例：灵感枯竭](clay-character-illustrations/assets/examples/12-approved-clay-style.png)

## 名称与目录

- GitHub 仓库建议名：`xiaolin-clay-illustrations`。
- 可安装技能文件夹与调用名称：`clay-character-illustrations`，调用时使用 `$clay-character-illustrations`。
- 仓库与技能名称不同是有意保留的，兼容现有用法。不要把仓库外层文件夹整个复制进 skills 目录。

```text
xiaolin-clay-illustrations/
├── README.md
├── LICENSE
└── clay-character-illustrations/
    ├── SKILL.md
    ├── LICENSE
    ├── NOTICE.md
    ├── agents/openai.yaml
    ├── references/
    └── assets/
        ├── character/     8 张角色、表情与造型图
        └── examples/      3 张海报配色参考 + 1 张已确认画风图
```

## 安装

在解压或克隆后的仓库根目录执行以下首次安装命令（macOS / Linux）。若已有同名技能，先备份并移出旧文件夹，再安装，避免新旧文件混合。

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./clay-character-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

生成和编辑需要运行环境提供内置 `image_gen` 工具及图像参考输入能力。本仓库不包含独立生图程序，不要求安装原版小黑技能；工具不可用时只能进行规划和编写提示词。

## 使用

生成单张配图：

```text
Use $clay-character-illustrations 用小林为“灵感枯竭”生成一张白底 3D 黏土配图。
```

只做规划：

```text
Use $clay-character-illustrations 先不要生图，为下面的文章规划 4 张配图，说明每张的核心意思、小林动作和必要物件。
```

换装编辑：

```text
Use $clay-character-illustrations 把这张图里的小林换成白衬衫、深蓝针织马甲和黑裙，保留人物表情、动作、道具、构图和白底。
```

## 角色与参考图

默认识别短语为“齐刘海红圈高马尾女生”。名字与识别短语不能替代图像参考。

- P0 核心身份：脸型、五官、齐刘海、发色、肤色、雀斑与头身比例。
- P1 标志造型：默认高马尾、红发圈、银色圈耳环，可按已提供变体调整。
- P2 场景变量：服装、表情、动作、视线和道具。
- S 画风：独立控制材质、光照、色彩与背景。

分级是本技能的描述规则，不是模型数值权重。详细规则见 [关键词与标准模板](clay-character-illustrations/references/ip-keywords.md)。

内置共 12 张参考图，详见 [图片索引](clay-character-illustrations/references/reference-index.md)。默认以 03 三视图锁定身份，12 已确认成图校准画风，通常每次选择 1–3 张必要参考，不需全部传入。海报仅提供指定的造型、材质与配色，不默认复制文字、标志、背景、版式或道具。

## 替换与维护

换角色身份时同步更新 [角色定义](clay-character-illustrations/references/character-ip.md)、关键词、prompt 和验收规则。换服装时更新对应造型图及图片索引；只换画风时更新 12 画风参考及 [画风定义](clay-character-illustrations/references/style-dna.md)。

保持文件名可减少路径修改；改名后需要同步所有引用。模板中的变量是有意保留的任务字段，生成前需填写。更新图片不会自动重写文字规则，更新仓库也不会自动同步到已安装副本。

## 验证与边界

已在本次制作过程中实际生成“灵感枯竭”图并完成通勤换装，确认了该画风；上传包已检查技能格式、引用路径、图像完整性、元数据、数量和打包内容。后续整理的标准模板尚未重新进行完整生图回归，不保证跨角度、复杂动作或多图生成时所有细节完全一致。

## 来源与许可

文字工作流改编自 [Ian 的 ian-xiaohei-illustrations](https://github.com/helloianneo/ian-xiaohei-illustrations)，保留原项目的 [MIT License](LICENSE) 和 [来源说明](clay-character-illustrations/NOTICE.md)。

小林名称与原始参考图由用户提供。文本工作流的 MIT License 不自动授予参考图片、其中品牌或其他素材的权利；图片来源说明见 NOTICE。
