<div align="center">

# cnfl-training-coach

「练了三年，还是跑不快——除非你把科学装进 AI。」

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#) [![Claude Code Skill](https://img.shields.io/badge/Claude_Code-Skill-blueviolet)](#) [![skills.sh Compatible](https://img.shields.io/badge/skills.sh-Compatible-brightgreen)](#) [![爆发力运动](https://img.shields.io/badge/橄榄球_篮球_排球_田径-FF3C00)](#)

**把顶级运动科学家的训练体系蒸馏成 AI 教练——覆盖美式橄榄球、篮球、排球、田径短跑等爆发力主导运动。**

打开 AI，输入你的运动项目和身体数据，就能按运动科学框架帮你诊断问题、生成周计划、处理伤病。

[效果示例](#效果示例) · [安装](#安装) · [使用](#使用) · [知识库](#知识库)

</div>

---

## 效果示例

输入体测数据之后：

```
用户    › WR，76kg，3年训练，后蹲140，40码5.1秒，右脚踝崴过

教练   › 诊断完成。你的问题不是力量不够——是力量没有转化成速度。

        后蹲 140kg = 1.84 倍体重，属于力量主导型运动员。
        但 40 码 5.1 秒说明弹性/反应力严重滞后于力量水平。

        根本问题：你的 SSC（牵张-缩短周期）太慢，
        脚踝在地面接触时没有弹性——力量没传出去，全靠肌肉硬撑。

        ── 赛季前 50 天方案 ──
        优先级 1：Spring Ankle 系统（每日，不可省）
        优先级 2：French Contrast 复合训练（每周 2 次）
        优先级 3：Flying Sprints 30m（每周 2 次）
        暂停：最大力量训练（赛前不加重量，加速度）
```

遇到伤病之后：

```
用户    › 脚踝崴了，副韧带拉伤，现在第 5 天，还肿着

教练   › 副韧带拉伤评估：
        当前阶段：亚急性期（3-14天），保护性负重阶段

        ── 现在可以做 ──
        · 等长收缩：脚踝 4 方向各 10 秒 × 3 组（不引发疼痛）
        · 非负重上肢训练正常进行
        · 坐姿直腿抬高保持股四头肌激活

        ── 禁止 ──
        · 任何跑动、跳跃、变向
        · 用力背屈（会牵拉韧带）

        ── 进入第二阶段的标准 ──
        单腿站立 > 10 秒无疼痛，肿胀消退 > 70%

        ⚠️ 以上为训练指导参考，不构成医疗诊断。
```

---

## 安装

### Claude Code（推荐）

```bash
git clone https://github.com/potato-uu/cnfl-training-coach ~/.claude/skills/cnfl-training-coach
```

安装后重启 Claude Code。输入"生成我的训练计划"、"我崴脚了"、"40码怎么提升"等触发词即自动激活。

### 直接粘贴给任意 AI（无需安装）

复制 [SKILL.md 原始内容](https://raw.githubusercontent.com/potato-uu/cnfl-training-coach/main/SKILL.md)，粘贴到对话开头即可：

```
[粘贴 SKILL.md 全文]

---
以上是你的角色设定，现在开始。我的信息：
位置: WR，体重: 76kg ...
```

适用于豆包、DeepSeek、ChatGPT、Kimi 等任意对话 AI。

### 其他 AI 工具

将 `SKILL.md` 内容粘贴为系统提示词：

| 工具 | 操作 |
|------|------|
| OpenClaw | 作为 Agent system prompt 注入 |
| Cursor / Windsurf | 粘贴为 Project Rules |
| ChatGPT / Gemini | 粘贴为 Custom Instructions |
| 任意 LLM API | 作为 `system` message 传入 |

---

## 使用

打开任意 AI（豆包 / DeepSeek / ChatGPT / Claude / Kimi），粘贴以下格式发送：

```
位置: WR / QB / OL / DB / LB / ...
体重: __kg，身高: __cm
训练年限: __年，训练频次: __天/周
设备: 杠铃 / 哑铃 / 跳箱 / 阻力带 / ...

力量: 后蹲__ / 前蹲__ / 高翻__ / RDL__ / 单腿RDL__
上肢: 卧推__ / 引体__
速度: 40码__ / 10码__ / 5-10-5__
跳跃: 垂直跳__cm / 立定跳远__m

伤病: （如有）
赛季开始: （日期）
```

---

## 知识库

| 模块 | 来源 | 核心内容 |
|------|------|----------|
| 速度 & 弹性 | Joel Smith / Just Fly Sports | SSC / RSI / 脚踝刚度 / Sprint mechanics |
| 垂直跳专项 | Kelly Baggett / Vertical Jump Bible（书） | 慢SSC vs 快SSC判断 / 深度跳量化标准 / 18+训练方案选择逻辑 |
| 能量系统 | Joel Jamieson / Ultimate MMA Conditioning（书） | 三系统关键数字 / 有氧-乳酸-磷酸原训练方法 / RSA协议 / 全年周期化 |
| 关节活动度 | Pavel Tsatsouline / Super Joints（书） | 17个日常关节流程 / 主动vs被动柔韧诊断 / 三阶段关节健康评估 |
| 周期化 | Cal Dietz / Triphasic Training（书） | 三相训练 / French Contrast / 训练残留 |
| 力量爆发力 | Garage Strength + Overtime Athletes | 变向减速优先 / 爆发力周期化 |
| 脊柱康复 | Stuart McGill / Back Mechanic（书） | Big 3 / 疼痛分类 / 自评流程 |
| 动作评估 | Gray Cook / Athletic Body in Balance（书） | FMS 7 测试 / 关节序列 / 纠正层级 |
| 运动表现 | Kelly Starrett / Becoming a Supple Leopard（书） | 扭矩定律 / 组织松动 / 动作标准 |
| 肩膀康复 | Mike Reinold | 投手十项 / 肩胛骨协议 / 复出六步 |
| 锋线专项 | CNFL 内部训练文件 | OL/DL 5 天分化方案（橄榄球专用） |

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
    ├── knowledge-rehab-experts.md    # 康复专家 (McGill / Starrett / Cook / Reinold)
    ├── knowledge-sports-medicine.md  # 分伤病类康复协议
    ├── knowledge-stan-protocols.md   # 个性化缺陷修复协议（示例）
    └── knowledge-lineman-training.md # 锋线专项训练计划
```

---

<div align="center">

⚠️ 本 Skill 提供训练参考，不构成医疗诊断。伤病请及时就医。

Made for CNFL 🏈 · potato-uu

</div>
