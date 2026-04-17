<div align="center">

# Sports-training-coach

「练了三年，还是跑不快——除非你把科学装进 AI。」

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#) [![Claude Code Skill](https://img.shields.io/badge/Claude_Code-Skill-blueviolet)](#) [![skills.sh Compatible](https://img.shields.io/badge/skills.sh-Compatible-brightgreen)](#) [![爆发力运动](https://img.shields.io/badge/橄榄球_篮球_排球_田径-FF3C00)](#)

**把顶级运动科学家的训练体系蒸馏成 AI 教练——覆盖美式橄榄球、篮球、排球、田径短跑等爆发力主导运动。**

打开 AI，输入你的运动项目和身体数据，就能按运动科学框架帮你诊断问题、生成周计划、处理伤病。

[效果示例](#效果示例) · [安装](#安装) · [使用](#使用) · [知识库](#知识库)

</div>

**English:** An AI coaching skill for explosive-sport athletes (American football, basketball, volleyball, track & field sprints/jumps). Feed it your test data and it returns a diagnosis → periodized weekly plan → injury management pipeline. Works with Claude Code, any LLM API, Cursor, or paste-into-chat.

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

### 直接粘贴给 AI（支持长上下文的环境）

复制 [SKILL.md 原始内容](https://raw.githubusercontent.com/potato-uu/cnfl-training-coach/main/SKILL.md)，粘贴到对话开头即可：

```
[粘贴 SKILL.md 全文]

---
以上是你的角色设定，现在开始。我的信息：
位置: WR，体重: 76kg ...
```

### 各平台兼容性

| 工具 | 支持情况 | 操作方式 |
|------|----------|----------|
| Claude Code | ✅ 完整支持 | 安装到 `~/.claude/skills/`，自动触发 |
| OpenClaw Agent | ✅ 完整支持 | 作为 Agent system prompt 注入 |
| DeepSeek / Kimi / 豆包 | ✅ 完整支持 | 粘贴 SKILL.md 全文到对话开头 |
| 任意 LLM API | ✅ 完整支持 | 作为 `system` message 传入 |
| Cursor / Windsurf | ✅ 完整支持 | 粘贴为 Project Rules / Global Rules |
| ChatGPT Custom Instructions | ⚠️ **不兼容** | Custom Instructions 限 1500 字符，SKILL.md 约 46KB，无法直接粘贴 |
| ChatGPT GPT / Project | ✅ 部分支持 | 创建 GPT 或 Project，将 SKILL.md 上传为知识文件 |
| Gemini Custom Instructions | ⚠️ **不兼容** | 字符限制同样不足以容纳完整 SKILL.md |

---

## 使用

打开任意 AI（豆包 / DeepSeek / ChatGPT / Claude / Kimi），粘贴以下格式发送：

```
姓名/代号: __
年龄: __岁
位置: WR / QB / OL / DB / LB / ...
体重: __kg，身高: __cm
训练年限: __年，训练频次: __天/周
训练时间段: __:__–__:__（例如 18:30–21:00）
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
| 冲刺力学 | Charlie Francis / Speed Trap（书） | "Less Is More"哲学 / CNS疲劳管理 / 三期化周期 / 赛前10天减量协议 |
| 协调力学 | Frans Bosch / Strength Training and Coordination（书） | 自由度问题 / CPG / 吸引子状态 / 肌腱弹性储能 / 深蹲≠速度 |
| 提示语言 | Nick Winkelman / The Language of Coaching（书） | 外部vs内部焦点 / OPTIMAL理论 / 爆发力动作提示表 / 表现vs学习区分 |
| 肌腱病康复 | Alfredson + Jill Cook（12篇同行评审） | 离心协议 / 三阶段连续体 / 等长止痛 / 跟腱/髌腱/腘绳肌分册 |
| 营养与恢复 | Aragon / Galpin / Norton / Israetel | 蛋白1.6-2.2g/kg / 亮氨酸阈值 / 睡眠8-10h / HRV晨测 / 恢复手段分级 |
| 篮球专项 | NSCA / Ben Shear / Alan Stein / PJF Performance | 位置需求矩阵 / COD五大模式 / 垂直跳专项化 / 赛季内负荷管理 / 踝ACL髌腱预防 |
| 排球专项 | Sheppard&Newton / Sattler / Marques / FIVB | 位置需求 / 三步助跑力学 / 肩部扣球量管理 / 髌腱预防 / Rally能量系统 |
| 田径专项 | Dan Pfaff / Stuart McMillan / Boo Schexnayder / Ralph Mann / Tony Holler | 加速阶段训练 / 最高速力学 / 速度耐力 / 跳跃项目 / 周期化 |
| 变向力学 | Myszka / Sheppard & Young / Dodoo（39篇来源） | 反应性敏捷 / COD Deficit / 末步力学 / 感知-动作耦合 / ACL预防 |
| 青少年发展 | Balyi / Lloyd & Oliver / Faigenbaum | LTAD 7阶段 / PHV敏感期 / 青少年跳跃分层标准 / 早期专项化风险 |
| 上肢爆发力 | Cressey / Baker / Reinold / Dietz（25篇来源） | 肩胛力偶 / 髋肩分离 / 拉推比2:1 / 法式对比上肢版 / QB/排球/篮球专项 |
| 运动心理 | Orlick / Rotella / Gould / Gervais | IZOF / 赛前准备模板 / 焦虑重评 / 3步错误恢复 / PETTLEP意象 |
| 力-速度诊断 | Samozino / Morin / Cross / Baker（20篇来源） | FVimb计算 / 力量vs速度缺陷诊断 / 训练处方决策表 / 运动专项曲线基准 |
| 周期化（线性） | Bompa / Periodization Theory and Methodology（书） | 宏观/中观/微观周期 / 运动素质金字塔 / 年度双峰计划 |
| 周期化（非线性） | Verkhoshansky & Siff / Supertraining（书） | 系列化/块化训练 / 联合效应 / 延迟转化效应 |
| 周期化（三相） | Cal Dietz / Triphasic Training（书） | 三相训练 / French Contrast / 训练残留 |
| 力量原理 | Zatsiorsky & Kraemer / Science and Practice of Strength Training（书） | 最大努力/重复努力/动态努力法 / 力-速度曲线 / 训练周期化 |
| 力量科学（综合） | NSCA / Essentials of Strength & Conditioning（书） | 生理学基础 / 测试评估 / 分期模板 / 球类运动专项 |
| Tier System | Joe Kenn / Coach's Strength Training Playbook（书） | 美式橄榄球周期化 / 3天分化 / 爆发-力量-辅助 |
| 位置专项 | David（NCAA QB）教学视频 | 四分卫专项力学 / 训练 focus / 实战案例 |
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
├── SKILL.md                          # 主 Skill 文件（AI 读取，运行时诊断行为）
├── CONTRIBUTING.md                   # 体系扩展与贡献指南（自更新协议/新增运动/回归测试）
├── LICENSE                           # MIT + 内容来源声明
├── README.md                         # 本文件
├── .gitignore                        # 屏蔽 profiles/ 个人档案
├── evals/                            # 黄金回归测试
│   ├── README.md                     # 运行方式
│   └── cases.md                      # 16 个黄金案例
├── profiles/                         # 本地私有档案（.gitignore，不进 repo）
│   └── README.md                     # 模板：knowledge-[athlete-id]-protocols.md
└── references/
    ├── exercise-library.md                      # 动作库
    ├── knowledge-basketball.md                      # 篮球专项
    ├── knowledge-bompa-periodization.md         # Bompa 线性周期化（书）
    ├── knowledge-cal-dietz.md                   # Cal Dietz Spring Ankle / Triphasic 蒸馏
    ├── knowledge-cod-agility.md                 # 变向力学（Myszka/Sheppard/Dodoo）
    ├── knowledge-coordination-mechanics.md      # 协调力学（Frans Bosch）
    ├── knowledge-cueing-science.md              # 提示语言（Winkelman）
    ├── knowledge-david-ncaa-qb.md               # NCAA QB 专项训练（David 视频）
    ├── knowledge-energy-systems.md              # 能量系统（Jamieson）
    ├── knowledge-fv-profile.md                  # 力-速度曲线诊断（Samozino/Morin）
    ├── knowledge-garage-strength-overtime.md    # 变向+爆发力周期化
    ├── knowledge-joe-kenn-tier.md               # Tier System（Joe Kenn 书）
    ├── knowledge-joel-smith.md                  # 速度+弹性（Just Fly Sports）
    ├── knowledge-lineman-training.md            # 锋线专项 5 天分化
    ├── knowledge-ltad-youth.md                  # 青少年长期发展（Balyi/Lloyd&Oliver）
    ├── knowledge-mobility.md                    # 关节活动度（Tsatsouline）
    ├── knowledge-nsca-football.md               # NSCA 橄榄球力量训练（书）
    ├── knowledge-nutrition-recovery.md          # 营养与恢复计时
    ├── knowledge-rehab-experts.md               # 康复专家（McGill/Starrett/Cook/Reinold）
    ├── knowledge-sport-psychology.md            # 运动心理（Orlick/Rotella/Gould）
    ├── knowledge-sports-medicine.md             # 分伤病类康复协议
    ├── knowledge-sprint-mechanics.md            # 冲刺力学（Charlie Francis）
    ├── knowledge-supertraining.md               # Supertraining（Verkhoshansky & Siff 书）
    ├── knowledge-tendinopathy.md                # 肌腱病康复（Alfredson + Cook）
    ├── knowledge-track-field.md                     # 田径专项
    ├── knowledge-triphasic-book.md              # Triphasic Training（Cal Dietz 原著）
    ├── knowledge-upper-body-power.md            # 上肢爆发力（Cressey/Baker/Reinold）
    ├── knowledge-vertical-jump.md               # 垂直跳专项（Baggett 书）
    ├── knowledge-volleyball.md                      # 排球专项
    └── knowledge-zatsiorsky.md                  # 力量训练科学（Zatsiorsky & Kraemer 书）
```

**注：** `profiles/` 目录被 `.gitignore` 屏蔽。每位使用者在本地存放自己的 `knowledge-[athlete-id]-protocols.md`（个人缺陷修复处方 / 体重 / 1RM / 伤病史）。模板见 `profiles/README.md`。

---

<div align="center">

⚠️ 本 Skill 提供训练参考，不构成医疗诊断。伤病请及时就医。

Made for CNFL 🏈 · potato-uu

</div>
