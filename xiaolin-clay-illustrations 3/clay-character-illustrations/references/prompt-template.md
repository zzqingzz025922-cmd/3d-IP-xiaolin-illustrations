# 小林生图与改图模板

按索引选择、查看并实际传入必要参考图，通常 1–3 张。填写变量并逐一说明输入图用途，不直接发送占位符。

关键词结构与中文模板见 [IP 关键词与分级](ip-keywords.md)。下面按相同结构执行：P0 是核心身份，P1 是默认可覆盖造型，P2 是场景可变项，S 是画风；这些分级不是模型数值权重。

## 新场景

```text
Create one standalone 16:9 landscape editorial illustration featuring Xiaolin (小林).

Input references and roles:
{List supplied images with roles: identity/turnaround; user-approved clay rendering reference; optional outfit/expression. The approved rendering reference guides material/light/color only, not outfit, expression, bulb props or squeezing pose.}

Recognition phrase: blunt-bangs girl with a red-tied high ponytail (default look, not a model-specific trigger token).
P0 Character identity:
Preserve Xiaolin's recognizable rounded face, large dark-brown eyes, thick upper eyelashes, pink eye makeup, peach skin with rosy cheeks and fine freckles, small nose and lips, prominent ears, oversized head and small stylized body. Near-black dark-brown hair, thick blunt straight bangs and short face-framing strands. Keep the same face and proportions through pose and outfit changes.

P1 Signature look and P2 Outfit:
Default signature look: high wavy ponytail with vivid red tie and silver hoop earrings. Follow an explicitly selected approved hairstyle/accessory variant when requested.
{Choose ONE provided reference outfit and its hairstyle. Default: charcoal T-shirt, cuffed denim shorts, dark chunky pull-on ankle boots, high wavy ponytail with red tie. Approved loose-hair/hat variants follow the selected reference rather than forcing a ponytail.}

P2 Scene variables:
Theme: {主题}
Core idea: {一句话核心意思}
Scene and action: {小林动作与物件如何表达概念}
Objects: {少量必要物件}
Expression: {符合主题，保留五官身份}

S Rendering, lighting and color:
Match the user-approved white-background clay rendering reference: 3D clay collectible-character style, rounded sculpted forms, soft studio light, tactile skin and sculpted hair. Preserve refined fabric, knit and denim details where appropriate; allow restrained sheen on eyes, lips and hair and small silver jewelry reflections. Match the approved rendering's brightness and saturation, with natural peach skin and dark-hair depth; garment colors follow the selected outfit reference. No automatic global saturation boost or lifting every dark color. No hand-drawn outlines, washed-out highlights or all-over glossy plastic.

Background and composition:
PURE WHITE seamless background regardless of peach or colored reference backgrounds. Short subtle contact shadows on the white ground plus natural shading on forms. One Xiaolin in one clear scene unless comparison/storyboard is requested. Ample negative space, safe margins around hair, footwear and props, subject group roughly 40–60% of canvas width. Reference sheets guide identity, not multi-character layouts; posters guide selected colors/materials, not composition or typography.

Text: {Default no text; if requested quote short exact labels.}
Avoid: copied poster words, logos, dates, selection handles, unnecessary titles, watermark, extra characters, irrelevant reference poses or props, malformed hands and extra limbs.
```

## 颜色校准

传入成图作为编辑目标，需要时增加一张小林参考：

```text
Edit only the target image's color grading to match the supplied Xiaolin reference's brightness, saturation, natural peach skin and dark-hair depth. Keep the output background pure white even if the reference has a peach or colored background. Preserve facial detail, highlights, clothing colors and subtle clay/material shading. Do not simply increase all saturation or brighten every dark region. Preserve identity, expression, pose, anatomy, outfit, accessories, objects, icons, framing and aspect ratio. Add no objects or text.
```

若用户明确要求进一步提亮或加饱和，按本轮要求适度调整，不把参考图当作拒绝调整的理由。

## 其他局部编辑

```text
Edit the target image. Change only: {本次要改的内容}. Preserve: {需锁定的人物、姿势、服装、物件、材质、色彩、构图等}. Keep Xiaolin's identity, 3D clay rendering and pure white background unless explicitly requested otherwise. Add no unrelated objects or text.
```
