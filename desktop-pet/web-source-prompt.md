# Codex 桌宠网页版源图生成提示词

目标：让网页图像生成工具产出更容易被本地流程复用的桌宠源素材。优先生成“单行动作条”或“小批量源图”，再由 Codex 本地检查、修复、组装为最终 `8 x 11` 的 v2 桌宠 spritesheet。

不要一开始就强求网页工具生成完整 `8 x 11` 大图。完整大图看起来省事，但最容易出现假透明棋盘格、行列不准、动作混行、方向错误、角色漂移。更稳的做法是：每次生成一个标准动作行，合格的行直接复用，不合格的行单独重做。

## 推荐用法：逐行动作条

把下面提示词里的角色描述和动作行替换后使用。每次生成 `8` 帧、`1` 行、透明背景。

```text
Create a transparent-background 2D anime chibi sprite strip for a Codex desktop pet.

Character:
- [Describe the character: appearance, hairstyle, clothing, accessories, colors, personality]
- Keep the same character identity, face, hairstyle, outfit, accessories, body proportions, color palette, and art style in every frame.
- Full body visible in every frame, centered, no cropping, no cut-off hat, hair, hands, dress, or feet.

Canvas and layout:
- One horizontal sprite strip.
- Exactly 8 frames in one row.
- True alpha transparency only.
- No checkerboard background, no white background, no gray background, no solid-color background.
- No text, labels, numbers, watermark, border, grid lines, cell outlines, or UI elements.
- Equal spacing, consistent scale, consistent lighting, safe padding around the character.

Action row:
- Generate exactly this action: [idle / running right / running left / waving / jumping / failed sad / waiting curious / playful running / review thinking].
- The 8 frames must form one coherent animation strip.
- Do not mix unrelated actions in the same strip.
- Make the action clearly different from idle when it is not idle.

Style:
- Clean high-quality 2D chibi illustration.
- Crisp edges, soft shading, desktop-pet friendly proportions.
- Transparent PNG/WebP style source image.
```

## 标准动作行清单

按这个顺序生成和验收。已经合格的行不要重做。

```text
Row 0: idle / standing, subtle neutral variations, 8 frames
Row 1: running or walking to the right, clearly right-facing, 8 frames
Row 2: running or walking to the left, clearly left-facing, 8 frames
Row 3: waving / greeting, 8 frames
Row 4: jumping / excited hop, 8 frames
Row 5: failed / sad / disappointed, clearly not idle, 8 frames
Row 6: waiting / curious / asking / open hands, clearly not idle, 8 frames
Row 7: playful running / energetic movement, 8 frames
Row 8: review / inspecting / thinking / reading-like action, 8 frames
Rows 9-10: 16 look directions
```

## 方向行专用提示词

方向行建议单独生成，因为这是最容易左右反、角度重复、角色变形的部分。

```text
Create 16 transparent-background direction frames for the same 2D anime chibi Codex desktop pet character.

Character:
- [Describe the same character exactly: appearance, hairstyle, clothing, accessories, colors]
- Keep the same character identity, outfit, body proportions, color palette, and art style in all 16 frames.
- Full body visible, centered, no cropping.

Layout:
- Use exactly 8 columns and 2 rows.
- True alpha transparency only.
- No checkerboard, no white/gray/solid background, no labels, no borders, no grid lines.
- Equal spacing and consistent scale.

Direction order:
- Row 1: 000 up/back-up, 022.5 upper-right, 045 upper-right, 067.5 upper-right, 090 right, 112.5 lower-right, 135 lower-right, 157.5 lower-right.
- Row 2: 180 down/front-down, 202.5 lower-left, 225 lower-left, 247.5 lower-left, 270 left, 292.5 upper-left, 315 upper-left, 337.5 upper-left.

Requirements:
- 000 must not be a normal front-facing idle pose.
- 090 must clearly face right.
- 270 must clearly face left.
- The sequence must feel like a smooth rotation.
- Do not repeat the same side profile for many angles.
- Do not reverse left and right.
```

## 可选：完整 `8 x 11` 大图提示词

只有当网页工具能稳定生成严格网格时才使用这一版。生成后仍必须由 Codex 本地检查真假透明、行列尺寸、动作语义、方向顺序和角色一致性。

```text
Create a complete transparent-background 2D anime chibi desktop pet spritesheet.

Character:
- [Describe the character: appearance, hairstyle, clothing, accessories, colors, personality]
- Keep the same character identity, face, hairstyle, outfit, accessories, body proportions, and art style in every frame.
- Full body visible in every cell, centered, no cropping, no cut-off hat/hair/feet/hands.

Canvas and layout:
- One single spritesheet image.
- Exactly 8 columns and 11 rows.
- 88 frames total.
- Transparent background only, true alpha transparency.
- Do not use checkerboard background, white background, gray background, shadows-only background, or any solid color background.
- Keep equal spacing and consistent scale in every cell.
- Each frame should fit inside its cell with safe padding.

Required row meanings:
- Row 0: idle / standing, subtle neutral variations, 8 frames.
- Row 1: running or walking to the right, 8 frames, clearly right-facing.
- Row 2: running or walking to the left, 8 frames, clearly left-facing.
- Row 3: waving / greeting, 8 frames.
- Row 4: jumping / excited hop, 8 frames.
- Row 5: failed / sad / disappointed, 8 frames, clearly different from idle.
- Row 6: waiting / curious / asking / open hands, 8 frames, clearly different from idle.
- Row 7: running forward or playful energetic movement, 8 frames.
- Row 8: review / inspecting / thinking / reading-like action, 8 frames.
- Row 9: look directions 000, 022.5, 045, 067.5, 090, 112.5, 135, 157.5 degrees.
- Row 10: look directions 180, 202.5, 225, 247.5, 270, 292.5, 315, 337.5 degrees.

Look direction requirements:
- 000 must clearly show the character looking upward or back/up, not a normal front-facing idle pose.
- 090 must clearly face right.
- 180 must clearly show the character looking downward or front/down according to the same rotation logic.
- 270 must clearly face left.
- The 16 directions must form a smooth continuous rotation sequence.
- Do not repeat the same side profile for multiple angles.
- Do not reverse left and right.
- Do not change the character design across directions.

Animation requirements:
- Each row should read as one coherent animation strip.
- Keep pose changes natural and consistent within each row.
- Do not mix unrelated actions within the same row.
- Do not add props unless they are part of the character design.
- Avoid text, labels, numbers, watermarks, borders, grid lines, cell outlines, or UI elements.
```

## 生成后自检

拿到网页生成图后，先问自己这几件事：

```text
Is the background real alpha transparency, not a rendered checkerboard?
Are all body parts fully visible?
Are there exactly 8 frames in each generated strip?
Does each strip contain only one action?
Are right-facing and left-facing rows correct?
Are failed/waiting/review visibly different from idle?
Are the 16 look directions ordered correctly?
Did the character identity stay consistent?
```

如果只有一行或几个方向失败，只重做失败部分。不要因为局部失败就重做整张 spritesheet。
