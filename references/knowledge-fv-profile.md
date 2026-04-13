# 力-速度曲线诊断与训练处方 — Samozino / Morin / Baker

> 核心文献：Samozino et al. 2008/2012/2014/2016；Morin & Samozino 2016；Cross et al. 2017/2020；Baker 2001–2021
> 适用运动：橄榄球（WR/DB/LB）、篮球、排球、短跑、任何需要加速爆发的项目

---

## Part 1: F-V Profile 基础框架

### 1.1 力-速度关系是什么

**每个运动员的神经肌肉系统都有一条固定的力-速度权衡线：力越大，速度越慢。**

- F-V 曲线是线性的（垂直跳和冲刺均适用），不是抛物线
- 曲线两端：F₀ = 理论最大力（速度趋近于零时）；V₀ = 理论最大速度（力趋近于零时）
- 曲线中点：Pmax = 最大功率 = F₀ × V₀ / 4
- **关键洞见**：两个运动员可以有相同的 Pmax，但 F-V 曲线位置完全不同，训练处方因此截然不同
- 垂直方向（跳跃）与水平方向（冲刺）的 F-V 曲线相互独立，需分别评估

**反直觉点：** 提升 Pmax 不一定提升运动表现——如果曲线位置偏离最优，哪怕 Pmax 很高，实际爆发力输出也受限。

---

### 1.2 两种缺陷类型

**运动员不是力量不足，就是速度不足——极少有人恰好在最优点。**

| 缺陷类型 | 表现特征 | 典型运动员类型 |
|---|---|---|
| Force-deficit（力量缺陷） | 能快速移动但冲击力不足；重训 1RM 低；垂直跳推进时间长 | 纯速度型运动员、轻体重球员、以有氧为主的运动员 |
| Velocity-deficit（速度缺陷） | 力量大但启动慢；反应时间长；冲刺前程加速差 | 过度力量训练的运动员、体重过大的运动员、大量深蹲却不练跳跃者 |

- 只做重训的运动员：F₀ 升高，V₀ 下降 → 曲线向力量端漂移 → 速度缺陷
- 只做速度/技术训练的运动员：V₀ 提升，F₀ 停滞 → 力量缺陷
- NFL 大拿（线锋）：绝对力量最高，但归一化后 77% 被归类为**力量缺陷**（原因：体重太大，F₀/kg 低）

**反直觉点：** 深蹲 500 磅的前锋，按体重归一化后往往是"力量缺陷"。

---

### 1.3 最优 F-V Profile 的含义

**最优不等于"力量最大"或"速度最快"，而是两者的特定比例。**

- Samozino 2012/2014 推导出：对于给定的 Pmax，存在一个 F-V 斜率（SFV_opt）使爆发力表现最大化
- SFV_opt 公式（跳跃）：`SFV_opt = -(2 × m × g × h_opt) / (hPO × V₀²)`
  - m = 体重 (kg)；g = 9.81；hPO = 推蹬距离（下蹲到最高点的 CoM 位移，约 0.35–0.45 m）
- **最优比率不是固定的**，它因运动员的推蹬距离（腿长、下蹲深度）不同而变化
- 冲刺的最优 F-V 与跳跃的最优 F-V **不同**——两者应分别测试和处方
- 更大的推蹬距离（更深的下蹲）→ 最优点向力量端移动
- 短距离加速（5–10 m）比最高速（30–40 m）更需要偏向 F 端

**反直觉点：** 腿长的运动员理论最优点比腿短的运动员更偏向"力量"侧。

---

### 1.4 FVimb 计算公式

**FVimb 是量化"实际曲线偏离最优曲线多远"的单一数字。**

```
FVimb (%) = SFV_actual / SFV_opt × 100
```

- SFV_actual = 实际 F-V 曲线的斜率（负值）= (F₀ - F_at_V₀) / V₀ = -F₀/V₀
- SFV_opt = 理论最优斜率（根据 Samozino 公式计算）
- FVimb = 100% → 完全平衡，实际曲线 = 最优曲线
- FVimb < 100% → 力量缺陷（曲线斜率不够陡峭）
- FVimb > 100% → 速度缺陷（曲线斜率过陡）

**分类阈值（Samozino 2013 + 实践共识）：**

| FVimb 值 | 分类 | 严重程度 |
|---|---|---|
| > 140% | 高度速度缺陷 (HVD) | 严重偏向力量端 |
| 110–140% | 低度速度缺陷 (LVD) | 轻度偏向力量端 |
| 90–110% | 平衡 (Balanced) | 无需矫正 |
| 60–90% | 低度力量缺陷 (LFD) | 轻度偏向速度端 |
| < 60% | 高度力量缺陷 (HFD) | 严重偏向速度端 |

---

## Part 2: 现场测试方法

### 2.1 方法 A：跳跃法（垂直 F-V Profile）

**原理：不同负重下的蹲跳（Squat Jump），用跳跃高度反推 F 和 V。**

**最小测试方案（Samozino 2008 验证）：**
- 需要：杠铃/哑铃 + 跳跃高度测量（接触垫/Vertec/手机 APP）
- 负重范围：0 kg（体重）→ 使跳高仅约 10 cm 的最大负重
- 常见负重组合（80 kg 男性运动员示例）：0、20、40、60 kg
- 最少点数：3 个负重（精度低），推荐 4–5 个
- 顺序：随机或从轻到重，每个负重最大努力跳 2–3 次取最佳

**计算输入：**
- 体重 (kg)
- 下肢长度（地面到大转子，单位 m）
- 每个负重下的最佳跳跃高度 (m)

**计算输出（Morin 的免费 Excel 表格）：**
- F₀ (N/kg)、V₀ (m/s)、Pmax (W/kg)
- SFV_actual、SFV_opt、FVimb (%)

**关键执行要求：**
- 严格无反向动作（Squat Jump，非 CMJ）——从静止蹲姿起跳
- 标准起始角度：膝关节 90°
- 手持杠铃/哑铃于肩部，不得借助上肢冲力

**反直觉点：** 不需要力台——跳跃高度 + 体重 + 腿长就足够计算 F₀ 和 V₀。

---

### 2.2 方法 B：冲刺法（水平 F-V Profile）

**原理：用分段计时数据重建整条加速段的 F-V-P 关系。**

**Samozino-Morin 模型（2016 验证，误差 < 5%）：**
- 输入：体重 + 身高 + 分段时间
- 计时门至少 4 个分段：5 m、10 m、20 m、30 m
- 推荐 5–6 个分段以提升精度（可加 15 m 或 40 m）
- 起跑要求：**静止站立**起跑（不能滚动起跑），第一个动作触发计时

**输出变量：**
- F₀_H：水平最大理论力（N/kg），典型范围 7–10 N/kg（男性精英）
- V₀_H：水平最大理论速度（m/s），典型范围 7.5–11 m/s
- Pmax_H：最大水平功率（W/kg）
- RF_max：最大力量有效比（%）——第一步推蹬中水平分力占总地面反力的比例
- DRF：力量有效比的递减率（%/m/s）——每提速 1 m/s，RF 下降多少

**精英参考数据（Morin et al. 2019, PLOS ONE）：**

| 运动项目 | F₀_H (N/kg) 男 | V₀_H (m/s) 男 |
|---|---|---|
| 世界级短跑 | ~11 | ~10.5–11 |
| 雪橇/冬季运动 | ~9.5–10 | ~9–10 |
| 排球/沙滩排球 | ~8.5–9 | ~8–9 |
| 足球精英 | ~8–9 | ~8.5–9.5 |
| 团队运动综合 | 7–10 | 7.5–10 |
| 女性精英 | 6–9 | 6–9.5 |

**RF 和 DRF 的实用意义：**
- RF_max 越高 → 起步阶段更有效率地水平推蹬
- DRF 越接近 0（斜率平缓）→ 在加速到高速时保持水平效率的能力越强
- DRF 差的运动员：起步不错但过渡到最高速时力量方向变垂直，效率下降

---

### 2.3 计时门精度注意事项（Morin & Cross 实践警告）

**计时误差会严重扭曲 F₀ 计算。**

- 推荐：计时门安装在运动员前方 20–50 cm 处，由运动员第一个动作触发
- 禁止："首次通过计时门"计时方式——会低估前 5 m 时间，导致 F₀ 大幅高估（可差 15–20%）
- 允许替代：激光枪 / 雷达枪（速度-时间数据，精度相当）
- 手机 APP（MySprint 等）：精度可接受，偏差通常在 1–3% 以内

---

### 2.4 方法 C：负重-速度（Load-Velocity）法（Baker VBT 方法）

**用杠铃速度直接建立力-速度关系，无需测试跳跃或冲刺。**

**Baker 推荐测试方案（深蹲为例）：**
- 使用速度测量设备（GymAware、Vitruve、Output Sports 等）
- 4–5 个负重：约 60–65%、70%、80%、90% 1RM，每档 1–2 次最大努力
- 记录每档的最佳平均速度（Mean Velocity）
- 画出负重-速度散点，最优线性拟合即为该运动员的 Load-Velocity Profile

**Baker 速度区间与训练目标映射：**

| 平均速度 (m/s) 深蹲 | 负重范围 | 训练目标 |
|---|---|---|
| < 0.5 | ≥ 90% 1RM | 绝对力量 |
| 0.5–0.75 | 80–90% | 加速力量 |
| 0.75–1.0 | 60–80% | 力量-速度 |
| 1.0–1.3 | 40–60% | 速度-力量 |
| > 1.3 | < 40% | 爆发力/弹性 |

**Baker 实用阈值：**
- 速度变化 ≥ 0.05 m/s（平均速度，最佳单次）→ 可认为力量水平有变化
- 速度变化 < 0.05 m/s → 噪音，不作为调整依据
- 深蹲 1RM 约在平均速度 0.30 m/s 处；卧推 1RM 约在 0.15 m/s 处

**与 Samozino 方法的对接：**
- Baker 的负重-速度斜率 = F-V 曲线斜率在重训动作上的体现
- 斜率陡峭（高负重才能维持速度）→ 运动员更偏力量端
- 斜率平缓（负重增加但速度下降不多）→ 运动员更偏速度端
- 实践整合：用跳跃法/冲刺法确定 FVimb，用 VBT 跟踪训练负荷调整效果

---

## Part 3: 训练处方逻辑

### 3.1 FVimb → 训练优先级决策表

**核心原则：针对缺陷端训练，不是强化已有优势。**

| FVimb | 诊断 | 主要训练方向 | 具体方法 | 辅助方法 |
|---|---|---|---|---|
| > 140% | 高度速度缺陷 | 速度优先 | 轻负重爆发动作、辅助冲刺、弹力绳辅助起跑 | 减少重训量，维持频率 |
| 110–140% | 低度速度缺陷 | 速度为主 + 功率 | 跳跃变体、Olympic lift 轻重量快节奏、弹振训练 | 重训降至 60–75% 1RM 快速完成 |
| 90–110% | 平衡 | 提升 Pmax 整体 | 力量与爆发力均衡发展，维持现有曲线位置 | 全区间训练 |
| 60–90% | 低度力量缺陷 | 力量为主 + 功率 | 重训 70–85% 1RM，重箱跳，负重跳 | 保留一定速度刺激 |
| < 60% | 高度力量缺陷 | 力量优先 | 大重量深蹲、髋推、RDL，≥ 85% 1RM | 暂时减少纯速度工作 |

---

### 3.2 力量缺陷的训练处方（FVimb < 90%）

**力量缺陷 = F₀ 过低，需提升高负重下的力输出上限。**

- 主要工具：后蹲（≥ 75% 1RM）、前蹲、罗马尼亚硬拉、髋推、力量举变体
- 负重区间：85–95% 1RM，每组 1–4 次，每周 2–3 次
- 辅助工具：负重箱跳（+20–30% 体重背心或杠铃）、负重蹲跳
- 旋翼机（Flywheel）：高偏心负荷，有效提升 F₀
- 斜坡推雪橇（75% 体重以上负重）：特异性水平力量刺激
- 阶段性目标：4–8 周内 FVimb 从 < 60% 提升至 70–85%

**量化标准（Baker 追踪）：**
- 深蹲同重量平均速度每 4 周提升 ≥ 0.03 m/s → 力量进步确认
- 0 kg 蹲跳高度不下降 → 速度端未因力量训练受损

---

### 3.3 速度缺陷的训练处方（FVimb > 110%）

**速度缺陷 = V₀ 过低，需提升高速下仍能产生力的能力。**

- 主要工具：辅助冲刺（弹力绳超速，速度提高 5–10%）、落地反跳、弹振式跳跃
- 轻负重（20–40% 1RM）以最大速度意图完成的发力动作
- 弹力绳辅助的蹲跳或跳跃变体
- 直线加速：轻阻力雪橇（≤ 10–15% 体重），侧重速度而非力量
- 下坡冲刺（3–5° 坡度）：超速训练，训练高速下的神经激活
- 跳跃密度（Plyometric Volume）：增加弹跳接触次数，每周 100–150 次接触为入门

**量化标准（Baker / Samozino）：**
- 0 kg 蹲跳平均速度提升 0.05 m/s → V₀ 提升信号
- 辅助冲刺最高速度提升 ≥ 0.3 m/s → V₀_H 改善确认

---

### 3.4 平衡后的 Pmax 提升策略

**两端都可以时，主攻曲线中点（Pmax），即最优负重下的最大功率。**

- 最优功率负重 ≈ 0 kg 跳跃最大速度对应的 30–50% 1RM 区间
- 哑铃/杠铃弹振深蹲：45–55% 1RM，速度意图最大化
- 跳跃深蹲（Jump Squat）：30–40% 1RM
- Olympic Lift：抓举/高翻，60–80% 1RM（兼顾 F 和 V）
- 雪橇加速：50–70% 体重负重（兼顾水平 F-V 曲线中点）
- 阶段性目标：每 6 周 Pmax 提升 3–5 W/kg

---

### 3.5 冲刺专项的训练处方（水平 F-V 视角）

**水平 F₀ 不足（sprint force-deficit）≠ 垂直力量不足；处方不同。**

- 水平力量缺陷（低 F₀_H）：
  - 重阻力雪橇（40–80% 体重）10–20 m 冲刺
  - 上坡冲刺（8–15% 坡度）×6–10 次
  - 后链专项训练：腘绳肌离心、Nordic Curl、GHR
  - 起步技术强调：向前倾斜，推蹬角度 ≤ 45°

- 水平速度缺陷（低 V₀_H）：
  - 无阻力最高速冲刺 30–60 m ×4–6 次（充分恢复 > 3 min）
  - 辅助下坡冲刺（2–5° 下坡）
  - 跑道飞跑（Flying Run）：15–30 m 最高速段计时

- DRF 改善（保持高速下水平效率）：
  - 重点：冲刺技术训练（前倾维持、步频节奏、后蹬角度）
  - 过渡速度区间（15–25 m 段）的重复冲刺训练

---

## Part 4: 运动专项应用与整合

### 4.1 与现有诊断的整合框架

**F-V Profile 补充，而非替代，现有测试体系。**

| 现有测试 | 提供信息 | F-V Profile 补充内容 |
|---|---|---|
| 后蹲 1RM | 绝对力量上限 | 力量在爆发速度下的可用比例 |
| CMJ / VJ 高度 | 纵向爆发力总量 | 垂直 F₀、V₀、FVimb 分解方向 |
| 40 码 / 10 码冲刺时间 | 速度结果 | 水平 F₀、V₀、RF、DRF 机制解释 |
| 体能测试综合 | 有氧/无氧能力 | F-V 曲线不受能量系统影响，独立评估 |

**整合决策流程：**
```
VJ 低 → 看 FVimb
  FVimb < 90%  → 力量缺陷 → 优先加重训练
  FVimb > 110% → 速度缺陷 → 优先加弹跳/速度
  FVimb 90–110% → 均衡 → 检查 Pmax，看能否整体提升

10 码慢 + 40 码也慢 → 看水平 FVimb
  低 F₀_H → 起跑推蹬力不足 → 重阻力雪橇 + 爆发力训练
  低 V₀_H → 过渡最高速能力差 → 无阻力高速冲刺 + 技术

深蹲强但 VJ 和 40 码平庸 → 速度缺陷概率极高
```

---

### 4.2 不同运动项目的 F-V 曲线位置

**没有统一的"理想"曲线——最优点因运动员肢体和任务而异，但有趋势规律。**

**水平 F-V Profile（冲刺）：**

| 运动 / 位置 | F₀_H 典型范围 (N/kg) | V₀_H 典型范围 (m/s) | 倾向 |
|---|---|---|---|
| 世界级短跑 | 9.5–11 | 10–11.5 | 高 F 高 V（世界标准） |
| NFL WR/DB/RB | 8.5–10 | 9–10.5 | 偏 V 端 |
| NFL 线锋 | 高绝对值，低相对值 | 7.5–9 | 易速度缺陷（按体重算） |
| 足球前锋/后卫 | 8–9 | 8.5–9.5 | 平衡或轻度偏 V |
| 橄榄球 | 8–9.5 | 8–9.5 | 接近平衡 |
| 篮球后卫 | 7.5–9 | 8–10 | 偏 V 端 |
| 排球主攻手 | 8–9.5 | 7.5–9 | 略偏 F 端（垂直跳主导） |

**垂直 F-V Profile（跳跃）：**
- 跳跃为主的运动（排球、篮球）→ 较高 F₀_V，重视垂直 FVimb
- 冲刺为主的运动（WR、DB、短跑）→ 优先水平 FVimb
- 两者都需要（RB、LB）→ 分别评估，按更大缺口优先处方

---

### 4.3 赛季内 vs 赛季外的 F-V 曲线漂移

**赛季内：曲线向速度端漂移。赛季外：可积极向目标方向调整。**

**观察规律（Morin et al. 足球季度研究 + Cross et al. 橄榄球研究）：**
- 赛季前大重量阶段：F₀ 提升，V₀ 轻度下降 → 曲线向力量端漂移
- 赛季中（大量比赛，无重训）：F₀ 下降，V₀ 相对维持 → 向速度端漂移
- 赛季末：力量缺陷风险最高（累计减少重训后）
- U14/U16/U18 足球：随赛季 F₀ 整体呈上升趋势，V₀ 较稳定

**实践策略：**
- 赛季外（Off-Season，12–20 周）：可激进地调整 FVimb，允许 4–6 周单向偏移
- 赛季内（In-Season）：维持 FVimb 在 ±15% 范围内，用最少训练量保持平衡
- 赛季内辅助/阻力冲刺（Resisted/Assisted Sprint）每周 2–3 次：可在 6–8 周内改变水平 F-V 斜率

---

### 4.4 橄榄球 WR/DB 专项分析

**WR/DB 是 F-V 测试价值最高的位置之一：需要极高 V₀ 同时保持爆炸性加速力。**

- 典型问题：只重力量房训练 → 速度缺陷
- 次要问题：只做速度训练无重训 → 力量缺陷（加速段弱）
- 目标 FVimb：90–110%（平衡），但 V₀_H ≥ 9.0 m/s（绝对值必须达标）
- 关键测试段：5 m 和 10 m（F₀_H 影响最大）；30–40 m（V₀_H 影响最大）
- 训练分配建议：
  - 赛季外：30% 力量（if force-deficit）或 20% 力量（if balanced）+ 40% 速度/弹跳 + 20% 综合爆发力 + 10% 技术
  - 赛季内：每周 1 次重训 + 2 次速度（1 有阻力 + 1 无阻力）

---

### 4.5 常见训练错误

**最高频错误：只练力量导致速度缺陷，且教练浑然不知。**

**错误 1：大重量深蹲堆了 3 年，VJ 和 40 码不涨**
- 根因：F₀ 已经饱和，V₀ 长期未刺激 → 速度缺陷（FVimb > 130%）
- 修正：减少 > 85% 1RM 训练，增加跳跃密度和辅助冲刺

**错误 2：测 VJ 但不区分 CMJ 和 SJ**
- CMJ > SJ 超过 10–15%：反应力量好，弹性贡献大
- CMJ ≈ SJ：弹性利用差，需要更多 SSC 训练（Plyometric 优先）
- SJ 进行 FV 测试时必须用 SJ，CMJ 会因反向动作改变有效推蹬距离

**错误 3：不同赛季用同一训练计划**
- 赛季末运动员通常处于力量缺陷状态，但教练按"通用爆发力计划"处方 → 加重了不平衡

**错误 4：用 F-V 曲线预测运动表现（而不是诊断）**
- FVimb 是处方工具，不是排名工具
- 两个 FVimb 相同的运动员，Pmax 可能相差 40%，运动表现差距巨大
- 必须同时看 FVimb 和 Pmax 绝对值

**错误 5：计时门起跑位置错误**
- 触发门设在运动员前方 → 低估起跑时间 → F₀_H 高估 15–20%
- 解决：要求静止站立起跑，计时从运动员身体开始移动触发

---

### 4.6 最简版现场实施（零实验室条件）

**没有力台、没有计时门，只有秒表和杠铃。**

**最简版跳跃 F-V（需要：手机 + 杠铃/沙包）：**
1. 下载 MyJump2 或 Just Jump App（iOS，免费/低价）
2. 准备 3–4 个负重（体重、+10 kg、+20 kg、+40 kg）
3. 每个负重蹲跳 2 次取最高，记录跳高（cm）
4. 手动录入 Morin 的 Excel 模板（jbmorin.net 免费下载）
5. 得到 FVimb → 处方

**最简版冲刺 F-V（需要：手机 + 标记锥）：**
1. 下载 MySprint APP（iOS，约 $10）
2. 慢动作拍摄 30 m 冲刺全程
3. APP 自动识别过门时间，计算 F₀_H、V₀_H、RF、DRF
4. 精度：与计时门比较偏差 < 3%

**最简版 VBT（需要：Vitruve 或 RepOne，约 $200–300 设备）：**
1. 深蹲测试：60%、75%、90% 1RM 各 2 次最快速度
2. 手动画负重-速度散点图
3. 斜率对比上次 → 判断力量端或速度端进步

**没有任何工具的近似判断（经验法则）：**
- 运动员 VJ 高但冲刺慢 → 可能 V₀_H 不足（速度缺陷，水平向）
- 运动员冲刺快但 VJ 低 → 可能 F₀_V 不足（力量缺陷，垂直向）
- 深蹲 > 2× 体重但 VJ < 体重一半（50 cm）→ 速度缺陷高概率
- VJ > 70 cm 但深蹲 < 1.5× 体重 → 力量缺陷高概率

---

### 4.7 F-V Profile 的局限性与批评

**工具有效，但不是万能。了解边界条件才能正确使用。**

- **2023 年 IJSPP 争议论文**（"Sprint FV Profiling is a Dead End"）：
  - 反驳：FV profile 的线性假设在某些高速条件下失效
  - 回应（Samozino/Morin）：对于加速阶段（0–30 m）仍然有效；高速最大速度段需谨慎
  - 实践建议：将 F-V profile 用于**加速诊断**，而非最高速诊断

- **垂直 vs 水平独立性**：垂直 FVimb 不能预测水平 FVimb；需两者分别评估
  - 研究显示两者相关性低（r < 0.4）

- **FVimb 重复测试变异性**：
  - F₀_H：CV ≈ 3.5–5%（相对较高）
  - V₀_H：CV ≈ 1.5%（稳定）
  - 实践建议：FVimb 差异 < 10% 不做处方调整；仅 ≥ 15% 才有实际意义

- **儿童/青少年适用性**：青少年 F-V 曲线随成熟度显著变化，不宜用成人阈值判断

---

### 4.8 快速参考决策卡

```
┌─────────────────────────────────────────────────────────────────┐
│                    F-V PROFILE 快速决策流程                      │
│                                                                  │
│  测试 → 计算 FVimb (%) → 对照表 → 处方                           │
│                                                                  │
│  FVimb < 60%   │ 高度力量缺陷 │ → 最大力量优先（≥ 85% 1RM）      │
│  FVimb 60–90%  │ 低度力量缺陷 │ → 力量 + 功率复合               │
│  FVimb 90–110% │ 平衡         │ → 提升 Pmax，维持平衡            │
│  FVimb 110–140%│ 低度速度缺陷 │ → 速度 + 爆发力复合             │
│  FVimb > 140%  │ 高度速度缺陷 │ → 速度/弹跳优先（减重训量）      │
│                                                                  │
│  !! 同时检查 Pmax 绝对值 !!                                       │
│  FVimb 平衡但 Pmax 低 → 两端都需要提升，均衡训练                   │
│                                                                  │
│  冲刺慢 + 低 F₀_H → 重阻力雪橇 + 起跑技术                        │
│  冲刺慢 + 低 V₀_H → 无阻力高速冲刺 + 下坡                        │
│  DRF 差（斜率陡）→ 冲刺技术 + 过渡速度专项训练                    │
└─────────────────────────────────────────────────────────────────┘
```

---

## 核心文献索引

1. Samozino P et al. (2008). *A simple method for measuring force, velocity and power output during squat jump.* J Biomech.
2. Samozino P et al. (2012). *Optimal force-velocity profile in ballistic movements — Altius: Citius or Fortius?* Med Sci Sports Exerc.
3. Samozino P et al. (2013). *Force-velocity profile: imbalance determination and effect on lower limb ballistic performance.* Int J Sports Med.
4. Samozino P et al. (2016). *A simple method for measuring power, force, velocity properties, and mechanical effectiveness in sprint running.* Scand J Med Sci Sports.
5. Samozino P et al. (2021). *Optimal mechanical force-velocity profile for sprint acceleration performance.* Scand J Med Sci Sports.
6. Morin JB & Samozino P (2016). *Interpreting power-force-velocity profiles for individualized and specific training.* Int J Sports Physiol Perform.
7. Morin JB et al. (2011). *Technical ability of force application as a determinant factor of sprint performance.* Med Sci Sports Exerc.
8. Morin JB et al. (2019). *Sprint mechanical variables in elite athletes: Are force-velocity profiles sport specific or individual?* PLOS ONE.
9. Cross MR et al. (2017). *Force-velocity profiling in sled-resisted sprint running: optimal conditions for maximizing power.* Int J Sports Physiol Perform.
10. Cross MR et al. (2020). *Individual sprint force-velocity profile adaptations to in-season assisted and resisted velocity-based training in professional rugby.* J Strength Cond Res.
11. Cross MR et al. (2021). *Force-velocity profiling in athletes: reliability and agreement across methods.* PLOS ONE.
12. Cross MR et al. (2018). *Power-force-velocity profiling of sprinting athletes: methodological and practical considerations when using timing gates.* J Strength Cond Res.
13. Baker D (2001). *A series of studies on the training of high-intensity muscle power in rugby league players.* J Strength Cond Res.
14. Baker D & Newton RU (2005). *Methods to reliably estimate the 1-RM upper body strength from the 1-RM lower body strength.* J Strength Cond Res.
15. Delaney JA et al. (2018). *Sprint acceleration mechanical profiling for the NFL draft.* Sports Biomech.
16. Janicijevic D et al. (2021). *Force-velocity profiles in collegiate American football players.* Int J Strength Cond.
17. Jimenez-Reyes P et al. (2016). *Effectiveness of an individualized training based on force-velocity profiling during jumping.* Front Physiol.
18. Jimenez-Reyes P et al. (2019). *Seasonal changes in the sprint acceleration force-velocity profile of elite male soccer players.* Int J Sports Physiol Perform.
19. GymAware (2022). *Velocity zones and training prescription guidelines.* GymAware Technical Report.
20. SimpliFaster (2019). *Force-velocity profiling in sprinting and jumping — interview with Dr. Pierre Samozino.* SimpliFaster.com.
