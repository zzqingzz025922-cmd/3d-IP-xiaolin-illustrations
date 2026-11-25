# 小林标准生图与改图模板

先选择、查看并实际传入参考图。默认用 02 锁定身份、衣服、包与站姿，12 只提供渲染参考。不要把占位符原样发送给模型。分级见 [IP 关键词](ip-keywords.md)。

## 只有“小林 IP”的生成请求

```text
Generate one standalone full-body Xiaolin (小林) character illustration as a genuinely TRANSPARENT PNG cutout, approximately 2:3 portrait.
Input image 02 is the authoritative identity, default outfit, bag and standing-pose reference. If image 12 is supplied, use it for 3D clay material, lighting and color only; do not copy its expression, pose, bulb props or white background.

Preserve the recognizable rounded face, oversized head and small body, large dark-brown eyes, thick upper lashes, pink eyeshadow, peach skin with rosy cheeks and fine freckles, thick blunt straight bangs and near-black dark-brown hair. High wavy ponytail with red tie, silver hoop earrings.
Default outfit: white collared long-sleeve shirt; dark navy almost-black V-neck knitted vest with small gold buttons; black skirt; cream/white ribbed socks; black lace-up shoes; small black handbag held in one hand. Do not replace with a T-shirt, shorts, boots or an all-black pantsuit.
Default pose: front-facing full-body standing, calm half-lidded expression and slightly pouting lips, one hand holding the bag and the other resting naturally. No extra theme or props.

Refined 3D clay collectible-character render, rounded sculpted forms, soft studio illumination on the character, restrained sheen, fabric/knit detail, natural peach skin and dark-hair depth. Match the references' brightness and saturation.
Background must be real alpha transparency: no white, peach, black or painted checkerboard backdrop, no floor or cast-shadow haze. Keep white clothes opaque. Retain all hair, bag and shoes with safe transparent padding. No text, logos, watermark, extra people or cropped body parts.
```

实际工具调用还需设置 `transparent_background: true`，不只在 prompt 中写透明。

## 有主题的配图

沿用上述身份、默认穿搭与渲染段，替换站姿段并补充：

```text
Theme: {主题}
Core idea: {一句话核心意思}
Action and objects: {小林如何通过具体动作和少量物件表达概念}
Expression and gaze: {本次情绪与视线}
Outfit override: {仅在用户明确换装时填写，否则保持默认提包穿搭}
Composition: {默认 16:9 landscape for an article scene, or user-specified ratio}; one coherent isolated subject group with safe transparent margins.
Keep the default handbag unless explicitly changed; if both hands operate props, place the bag naturally beside her.
Output: genuinely transparent PNG, unless the user explicitly requests an opaque background.
```

## 用户明确要白底或场景

用用户指定背景替换透明段，并设置 `transparent_background: false`。白底不是默认，不把参考图的背景当作用户要求。

## 局部换装、调色与其他编辑

```text
Edit the target image. Change only: {明确要改的内容}.
Preserve: {本轮锁定的身份、表情、姿势、物件、构图等}.
Preserve the target's existing background and alpha transparency unless this edit explicitly requests a background change. Do not flatten an existing transparent image onto white.
Keep Xiaolin's recognizable face and 3D clay rendering. Add no unrelated props or text.
```

## 去背景

```text
Remove only the supplied image's background and floor. Deliver a genuinely transparent PNG with alpha, not a white/black/peach background or a painted checkerboard.
Preserve the full character, face, expression, pose, clothing, white shirt and socks, shoes, handbag, colors and 3D clay shading. Keep natural clean edges and transparent gaps inside bag handles and earrings. Add no objects or text.
```

去底设置透明模式；其他局部编辑保留目标原有透明度。保存后检查实际 Alpha，有透明背景且主体可见，不能仅检查文件后缀。
