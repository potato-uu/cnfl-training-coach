# CNFL Training Coach

**AI体能训练教练 — 专为中国CNFL业余橄榄球联盟设计**

基于顶级运动科学家知识蒸馏的体能诊断系统。输入你的数据，获得个性化训练计划和康复方案。

---

## 功能

- **力量诊断** — 后链不足、单侧失衡、力速转化缺陷检测
- **速度分析** — 40码/10码/5-10-5 分析 + Sprint mechanics
- **训练计划生成** — 按赛季阶段（季前/赛季/休赛期）定制周计划
- **增强式训练** — 基于 RSI / SSC 的 Plyometrics 周期
- **运动康复** — 6大类常见伤病（脚踝/腘绳肌/膝盖/腰背/肩膀/脑震荡）评估与分期康复
- **锋线专项** — OL/DL专项训练模板

## 知识库来源

| 分类 | 专家/资源 |
|------|----------|
| 速度/弹性 | Joel Smith (Just Fly Sports) |
| 周期化/三相训练 | Cal Dietz (Triphasic Training) |
| 力量&爆发力 | Garage Strength + Overtime Athletes |
| 脊柱/腰背 | Stuart McGill (Back Mechanic) |
| 动作评估 | Gray Cook (FMS / Athletic Body in Balance) |
| 运动表现 | Kelly Starrett (Becoming a Supple Leopard) |
| 肩膀/康复 | Mike Reinold |
| 锋线专项 | CNFL 内部训练文件 |

---

## 安装

### Claude Code（推荐）

```bash
git clone https://github.com/potato-uu/cnfl-training-coach ~/.claude/skills/cnfl-training-coach
```

安装后，在 Claude Code 中输入训练相关关键词（如"生成我的训练计划"、"我的40码是5.1秒"、"脚踝崴伤了"）即自动触发。

### 其他 AI Agent / LLM

将 `SKILL.md` 内容复制粘贴为系统提示词（System Prompt），可用于：
- **OpenClaw** — 直接作为 Agent system prompt
- **Cursor / Windsurf** — 粘贴为 Project Rules
- **ChatGPT / Gemini** — 粘贴为 Custom Instructions
- **任意 LLM API** — 作为 `system` message 传入

---

## 使用

输入你的数据，AI 会自动诊断并生成方案：

```
位置: WR
体重: 76kg，身高: 175cm
训练年限: 3年，训练频次: 5天/周
设备: 杠铃/哑铃/跳箱/阻力带

力量: 后蹲140 / 前蹲120 / 高翻110 / RDL 55 / 单腿RDL 25
上肢: 卧推90 / 负重引体+20
速度: 40码5.1 / 10码1.85 / 5-10-5 5.2
跳跃: 垂直跳70cm / 立定跳远2.85m

伤病: 右脚踝副韧带拉伤（2周前）
赛季: 2026-06-01
```

---

## 文件结构

```
cnfl-training-coach/
├── SKILL.md                          # 主 Skill 文件（AI 读取）
└── references/
    ├── exercise-library.md           # 动作库
    ├── knowledge-cal-dietz.md        # Cal Dietz 知识蒸馏
    ├── knowledge-joel-smith.md       # Joel Smith 知识蒸馏
    ├── knowledge-garage-strength-overtime.md
    ├── knowledge-rehab-experts.md    # 康复专家知识（McGill/Starrett/Cook/Reinold）
    ├── knowledge-sports-medicine.md  # 运动医学分伤病类协议
    ├── knowledge-stan-protocols.md   # 个性化缺陷修复协议（示例）
    └── knowledge-lineman-training.md # 锋线专项训练计划
```

---

## 免责声明

本 Skill 提供的所有建议仅供训练参考，**不构成医疗诊断**。如有伤病请及时就医或咨询物理治疗师。

---

*Made for CNFL 🏈 by potato-uu*
