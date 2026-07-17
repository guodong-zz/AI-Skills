Skill:
请读取我已连接的 GitHub 仓库 guodong-zz/AI-Skills 中的：desktop-pet/SKILL.md
严格按照该 Skill 定义的工作流处理我接下来提供的桌宠素材。优先复用已有合格内容，只修复或生成缺失、不合格的部分，并完成最终 QA、安装和复检。


web-source-pormot:
先生成8个row，再生成16个观察方向

8个row:先复制动作条模板，然后改Generate exactly this action: [idle / running right...]，这个要根据动作条里的具体动作来改。操作8次

16个观察方向：使用方向提示词生成，对应row9,row10'

自检无误后交给codex让其整合

想要便捷的可以直接使用8x11的提示词
