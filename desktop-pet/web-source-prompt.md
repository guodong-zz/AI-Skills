# Codex 桌宠网页版源图生成提示词
1.Base Prompt（固定部分）

Create a 2D anime chibi sprite strip for a Codex desktop pet.

Character:
- Use the provided reference image as the character identity.
- Keep the same face, hairstyle, outfit, accessories, color palette, body proportions, and art style.
- Do not redesign or add new elements.
- Keep the character consistent across all frames.
  
Layout:
- One horizontal sprite strip only.
- Exactly 8 frames in one row.
- No second row.
- No extra frames.
- Equal spacing between frames.
- Same character scale and position in every frame.
- Full body visible in every frame.
- No cropping of hair, hands, clothes, accessories, or feet.
 
Background:
- Transparent background preferred.
- Do not draw checkerboard patterns.
- Do not add scenery, floor, shadow background, gradient, or solid background.
- Keep the background clean for later alpha processing.

Style:
- High-quality 2D anime chibi style.
- Clean silhouette.
- Soft shading.
- Desktop-pet friendly proportions.

Restrictions:
- No text.
- No labels.
- No numbers.
- No watermark.
- No borders.
- No grid lines.

Use the same character from the provided reference image and previous approved sprite strips.

2.Action Modifier（每次替换）

Row 0 — Idle
Action:
Idle standing animation.
Generate subtle variations only:
- blinking
- breathing
- small hair movement
- slight posture changes
Do not walk, run, jump, wave, or change direction.

Row 1 — Walking Right
Action:
Walking or running toward the right.
Requirements:
- All frames must face right.
- Show a continuous walking/running cycle.
- Do not include left-facing frames.
- Do not generate multiple directions.

Row 2 — Walking Left
Action:
Walking or running toward the left.
Requirements:
- All frames must face left.
- Show a continuous walking/running cycle.
- Do not include right-facing frames.
- Do not generate multiple directions.

Row 3 — Greeting
Action:
Waving greeting animation.
Requirements:
- Clearly show a greeting gesture.
- Maintain the same standing position.
- Do not look like idle.

Row 4 — Jump
Action:
Excited jumping animation.
Requirements:
- Show a complete jump cycle:
  preparation → jump → landing.
- Keep full body visible.

Row 5 — Sad
Action:
Sad or disappointed animation.
Requirements:
- Clearly different from idle.
- Use visible sad posture:
  lowered head, weaker posture, disappointed expression.

Row 6 — Curious
Action:
Curious or waiting animation.
Requirements:
- Show curiosity or asking behavior.
- Use gestures such as head tilt or open hand.
- Clearly different from idle.

Row 7 — Playful
Action:
Energetic playful movement.
Requirements:
- More dynamic than normal walking.
- Maintain one coherent movement cycle.

Row 8 — Thinking
Action:
Thinking, reviewing, inspecting animation.
Requirements:
- Show focused or thoughtful behavior.
- Use existing accessories if possible.
- Clearly different from idle.

3. Direction Sheet Prompt（单独）

Create a direction sprite sheet for the same Codex desktop pet character.

Layout:
- Exactly 8 columns × 2 rows.
- Exactly 16 frames.
- No additional frames.
  
Character:
- Same identity, outfit, accessories, and style.

Direction order:
Row 1:
000 022.5 045 067.5 090 112.5 135 157.5
Row 2:
180 202.5 225 247.5 270 292.5 315 337.5

Requirements:
- 090 must clearly face right.
- 270 must clearly face left.
- Directions must form a smooth rotation.
- Do not duplicate side profiles.
- Do not randomly change poses.

3.完整 8×11

仅在网页模型已验证能稳定遵守复杂网格时使用。

```text
Create one complete 2D anime chibi Codex desktop pet spritesheet.

Use the same approved character identity throughout all 88 frames.

Strict structure:
- Exactly 8 columns.
- Exactly 11 rows.
- Exactly 88 frames.
- Do not add or remove rows.
- Do not merge cells.
- Do not create decorative margins, labels, row names, frame numbers, borders, or grid lines.

Rows:
Row 0: idle.
Row 1: walking or running right.
Row 2: walking or running left.
Row 3: waving / greeting.
Row 4: jumping / excited hop.
Row 5: failed / sad / disappointed.
Row 6: waiting / curious / asking.
Row 7: playful energetic movement.
Row 8: review / inspect / think / reading-like action.
Row 9: 000, 022.5, 045, 067.5, 090, 112.5, 135, 157.5.
Row 10: 180, 202.5, 225, 247.5, 270, 292.5, 315, 337.5.

Character consistency:
- Same face.
- Same hairstyle.
- Same outfit.
- Same accessories.
- Same body proportions.
- Same color palette.
- Same illustration style.
- Same approximate scale.

Background:
- Prefer true alpha transparency.
- Never draw a checkerboard pattern.
- If true alpha cannot be produced, use a clean plain near-uniform removable background.
```
