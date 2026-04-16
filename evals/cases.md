# 黄金案例 — 回归测试集

10 个覆盖运动/位置/经验/伤病/赛季阶段的典型 case。

---

## Case 1: WR 老兵 + 脚踝伤史 + 赛前

**Input：**
```
姓名: A.WR-Vet
运动: 美式橄榄球  位置: WR  A 组
年龄: 28  体重: 78kg  身高: 180cm
训练年限: 5  每周: 4 天
设备: 杠铃/哑铃/跳箱/阻力带
伤病: 2023 年右脚踝外侧韧带 Grade 2 扭伤，已完全康复 1.5 年
赛季开始日期: 60 天后

力量: 深蹲 145kg / RDL 85kg / 单腿RDL 30kg / 卧推 95kg
速度: 40 码 5.0 秒 / 5-10-5 4.7 秒
跳跃: 垂直跳 62cm / 立定跳远 2.7m
```

**Must have：**
- `current_phase = preseason`
- `posterior_chain_gap = moderate`（85/145 = 58.6%）
- `unilateral_gap = acceptable`（30/145 = 20.7%，处于临界）
- `injury_flag: ankle` 仍然触发，即使已康复（历史标记不消失）
- Spring Ankle Level 2 或 Level 3（5 年经验 + 历史伤）
- French Contrast 允许出现（训练年限 ≥ 3 年）
- 后链补课为 P1 或 P2

**Must not have：**
- 深度跳 > 40cm（脚踝标记限制）
- 忽略后链差距
- 给 offseason 最大力量块（现在是 preseason）

**Red flags：**
- 如果 40 码 5.0 被评为"strength-dominant"→ 错（要和 WR 基准 5.0 对比，刚好达标；但深蹲/体重 1.86 属力量主导，所以要看 balanced 还是 strength_dominant）

---

## Case 2: OL 新秀 + 休赛期 + 无伤

**Input：**
```
姓名: B.OL-Rookie
运动: 美式橄榄球  位置: OL  B 组
年龄: 24  体重: 108kg  身高: 185cm
训练年限: 2  每周: 5 天
设备: 杠铃/哑铃/雪橇/GHD/跳箱
伤病: 无
赛季开始日期: 120 天后

力量: 深蹲 170kg / 前蹲 130kg / RDL 100kg / 单腿RDL 40kg / 卧推 120kg
速度: 40 码 5.8 秒 / 5-10-5 5.3 秒
跳跃: 垂直跳 42cm
```

**Must have：**
- `current_phase = offseason`
- `posterior_chain_gap = moderate`（100/170 = 58.8%）
- 激活 `references/knowledge-lineman-training.md`（OL/DL 专项）
- 5 天分化方案建议
- Triphasic 或 Bompa 周期化（2 年经验允许书籍进阶）
- OL 基准放宽：B 组 40 码 5.8 秒（基准 5.6 + 0.2）可接受
- P0 = 最大力量（offseason + 无缺陷差距严重）

**Must not have：**
- French Contrast / 深度跳（2 年经验边界，OL 重体重额外谨慎）
- 把 OL 当 WR 处理（基准应放宽）
- 非橄榄球用户的纯速度优先处方

**Red flags：**
- 40 码 5.8 被标为 poor → 错（B 组 OL 基准内）

---

## Case 3: RB 急性 hamstring 拉伤

**Input：**
```
姓名: C.RB-Injured
运动: 美式橄榄球  位置: RB  A 组
年龄: 26  体重: 88kg  身高: 178cm
训练年限: 4  每周: 3 天
设备: 杠铃/哑铃/阻力带
伤病: 3 天前冲刺时右腿腘绳肌拉伤 Grade 2，尚未做 MRI
赛季开始日期: 45 天后
疼痛评分: 6/10，无法跑步，可慢走

力量（伤前）: 深蹲 160kg / RDL 110kg / 单腿RDL 40kg
速度（伤前）: 40 码 4.9 秒
```

**Must have：**
- **强制进入 Step 8 康复模式**（触发关键词：hamstring / 拉伤 / 3 天前）
- Grade 2 评估 + PEACE&LOVE 急性期协议
- 分期康复方案：Phase 1（0-2 周）+ Phase 2（2-4 周）+ Phase 3（复出）
- 当前可做训练：非受伤部位上肢、核心、对侧单腿
- 红色警告：出现明显血肿/无法负重/进行性加重 → 立即就医
- 康复边界声明："⚠️ 以上为训练指导参考，不构成医疗诊断"
- 跳过常规 Step 2-6 诊断流程或明确说明因伤推迟

**Must not have：**
- 冲刺训练
- Nordic Curl / 快速离心负荷
- 直接开新的 preseason 周计划（应以康复为主）
- French Contrast

**Red flags：**
- 忽略拉伤当普通训练 → 严重错误
- 建议 2 周后复出（Grade 2 至少 4-6 周）

---

## Case 4: 篮球主力 + 跳跃差 + 赛前

**Input：**
```
姓名: D.Bball-Forward
运动: 篮球  位置: 主攻/小前锋
年龄: 25  体重: 80kg  身高: 188cm
训练年限: 3  每周: 4 天
设备: 杠铃/哑铃/跳箱
伤病: 无
赛季开始日期: 50 天后

力量: 深蹲 110kg / RDL 70kg / 单腿RDL 25kg
速度: 30m 冲刺 4.5 秒 / 5-10-5 5.2 秒
跳跃: 垂直跳 42cm / 立定跳远 2.3m
```

**Must have：**
- 使用**篮球基准**（垂直跳 55cm、30m 4.4 秒、深蹲/体重 1.4x）
- 主要缺陷：垂直跳低于基准 13cm → P0 = 弹跳开发
- 深蹲/体重 1.375x，接近基准但略低
- 弹跳训练策略：判断快 SSC vs 慢 SSC（参考 knowledge-vertical-jump.md）
- 优先级应是：弹跳开发 > 变向 > 后链
- preseason 阶段 → 速度转化为主

**Must not have：**
- 使用橄榄球 WR 基准（40 码 5.0）
- 忽略篮球核心指标（垂直跳）
- 把 5-10-5 作为主要诊断（篮球 5-10-5 是补充，不是核心）

**Red flags：**
- 方案核心是冲刺训练 → 错（篮球核心是弹跳）

---

## Case 5: 排球新手 + 肩膀痛

**Input：**
```
姓名: E.Volley-Hitter
运动: 排球  位置: 主攻
年龄: 22  体重: 70kg  身高: 183cm
训练年限: 1  每周: 3 天
设备: 哑铃/阻力带
伤病: 肩膀右侧扣球时疼痛 2 周，外展 80-100 度疼痛弧
赛季开始日期: 赛季中（已开赛 3 周）

力量: 深蹲 75kg / RDL 50kg / 卧推 55kg
跳跃: 垂直跳 48cm
```

**Must have：**
- **触发 Step 8 康复模式**（关键词：肩膀 / 疼痛）
- `injury_flag: shoulder` + 过头推举禁忌
- Mike Reinold 肩袖康复协议（参考 knowledge-rehab-experts.md）
- 肩胛骨稳定训练（Thrower's Ten 或类似）
- Phase 分期 + 进阶标准（无痛外展 → 负荷进阶）
- inseason 阶段 → 维持力量 + 降量
- 训练年限 1 年 → 限制动作复杂度，不上 French Contrast
- 排球主攻基准：VJ 60cm，用户 48cm 低 12cm，但伤病优先不催进攻

**Must not have：**
- 杠铃过头推举（shoulder 伤）
- 忽略疼痛弧直接开训练
- French Contrast / Olympic Lifts（新手 + 伤病双重限制）

**Red flags：**
- 训练计划不提肩膀 → 严重错误
- 建议训练中疼痛可忍受继续练 → 错

---

## Case 6: 田径短跑 + 加速差 + 休赛期

**Input：**
```
姓名: F.Sprint-Track
运动: 田径短跑
年龄: 21  体重: 72kg  身高: 178cm
训练年限: 3  每周: 5 天
设备: 齐全（杠铃/跳箱/雪橇/GHD）
伤病: 无
赛季开始日期: 150 天后

力量: 深蹲 130kg / 前蹲 100kg / 高翻 75kg / RDL 85kg / 单腿RDL 32kg
速度: 10m 加速 2.05 秒 / 30m 4.3 秒
跳跃: 垂直跳 55cm / 立定跳远 2.8m
```

**Must have：**
- `current_phase = offseason`
- 使用短跑基准：30m 4.0 秒（用户 4.3，落后 0.3）、10m 1.85 秒（用户 2.05，落后 0.2）
- 深蹲/体重 1.81x → 力量基础充足
- 诊断：加速机制滞后 → P0 = 起跑/加速训练
- 引用 knowledge-sprint-mechanics.md（Charlie Francis）+ knowledge-fv-profile.md
- 后链 RDL/深蹲 65% → moderate gap，P1 或 P2
- Flying Sprints + 雪橇阻力 + Triphasic 离心块

**Must not have：**
- 橄榄球 40 码基准（应用 30m）
- 把 5-10-5 当短跑指标（短跑不依赖变向）

**Red flags：**
- P0 变成变向训练 → 错（短跑不需要变向）

---

## Case 7: 纯新手 + 篮球

**Input：**
```
姓名: G.Newbie
运动: 篮球  位置: 二传/自由人
年龄: 20  体重: 90kg  身高: 175cm
训练年限: 0  每周: 3 天
设备: 哑铃/阻力带/体重
伤病: 无
赛季开始日期: 90 天后

力量: 深蹲 60kg / RDL 40kg / 单腿RDL 15kg
速度: 30m 5.2 秒
跳跃: 垂直跳 30cm
```

**Must have：**
- 训练年限 0 → 强制基础动作模式期（前 8-12 周）
- 深蹲/体重 0.67x → 力量极度不足，P0 = 基础力量建立
- 动作复杂度限制：只上 Goblet Squat / Romanian Deadlift / 卧推 / 引体辅助
- **禁止动作**：高翻 / 高抓 / French Contrast / 深度跳 / 连续栏架跳
- 每个动作附带技术要点说明（新手学动作质量优先）
- 逐步引入单侧训练（几周后）
- 篮球基准应用但明确告知"先补力量基础，跳跃目标暂不谈"

**Must not have：**
- Triphasic 三相训练（新手不上）
- 任何高级周期化（Bompa/Supertraining 概念可引用但方案要简单）
- 直接给出垂直跳优先的进阶方案

**Red flags：**
- 给新手开 French Contrast → 严重错误
- 第一周就有高翻或深度跳 → 错误

---

## Case 8: 橄榄球精英 + 赛季中

**Input：**
```
姓名: H.Elite-WR
运动: 美式橄榄球  位置: WR  A 组
年龄: 29  体重: 82kg  身高: 185cm
训练年限: 7  每周: 5 天
设备: 齐全
伤病: 无
赛季开始日期: 已开赛 4 周，下场比赛 5 天后

力量: 深蹲 180kg / RDL 125kg / 单腿RDL 50kg / 卧推 130kg
速度: 40 码 4.75 秒 / 5-10-5 4.3 秒
跳跃: 垂直跳 82cm / 立定跳远 3.1m
```

**Must have：**
- `current_phase = inseason`
- 所有诊断为 `acceptable` 或优于基准
- 核心原则：**维持力量 + 降量 + 不加新刺激**
- 比赛 5 天前：减量日 / 只做激活 / 不做最大努力
- 赛季中训练安排：每周 1-2 次力量（低量高强）+ 恢复 + 球队训练
- HRV 监控 / 睡眠 / 主观疲劳评分建议
- 可用进阶工具：French Contrast（但赛季中限制频率，每 2 周 1 次而非每周）

**Must not have：**
- 引入全新训练块（偏离比赛日主要刺激）
- preseason 式高量冲刺
- 最大力量测试（inseason 禁忌）
- 深度跳大量（接触量需严控）

**Red flags：**
- 比赛前 2 天安排最大努力训练 → 严重错误
- 赛季中加 Triphasic 新块 → 错

---

## Case 9: 青少年 + 棒球 + PHV 敏感期

**Input：**
```
姓名: I.Youth-Pitcher
运动: 棒球  位置: 投手
年龄: 15  体重: 62kg  身高: 172cm（过去 12 个月长高 8cm）
训练年限: 1  每周: 3 天
设备: 哑铃/阻力带/体重
伤病: 无
赛季开始日期: 60 天后

力量: 深蹲 50kg / RDL 35kg
速度: 30m 4.8 秒
跳跃: 垂直跳 38cm
```

**Must have：**
- 识别 PHV（身高激增期）→ 启用 LTAD 框架
- 引用 knowledge-ltad-youth.md（Balyi/Lloyd&Oliver/Faigenbaum）
- 警告早期专项化风险（3.5x 伤病率）
- 动作模式优先于负荷
- 投手肩膀保护：限制 plyo push-up 容量、强调后侧肩袖
- 可引用 knowledge-upper-body-power.md 中肩胛稳定性
- 每周球类训练天数建议限制（青少年 overuse 风险）
- 避免最大强度 1RM 测试

**Must not have：**
- Olympic Lifts 大重量
- French Contrast / 深度跳高负荷
- 成人化的周期化方案
- 忽略 PHV 期关节韧带脆弱性

**Red flags：**
- 不识别青少年身份直接当业余成人处理 → 错
- 每周 5-6 天高强度训练 → 过载风险

---

## Case 10: 橄榄球 LB + 膝盖旧伤 + 赛季中

**Input：**
```
姓名: J.LB-Kneeissue
运动: 美式橄榄球  位置: LB  A 组
年龄: 27  体重: 95kg  身高: 183cm
训练年限: 4  每周: 4 天
设备: 杠铃/哑铃/跳箱/阻力带
伤病: 2 年前左膝 ACL 部分撕裂未手术，现蹲下时偶尔酸胀、高强度跳落地不稳
赛季开始日期: 已开赛 6 周，本周有比赛

力量: 深蹲 160kg（全蹲困难，半蹲）/ RDL 110kg / 单腿RDL 40kg / 卧推 115kg
速度: 40 码 5.2 秒 / 5-10-5 4.8 秒
跳跃: 垂直跳 65cm
```

**Must have：**
- `current_phase = inseason`
- `injury_flag: knee` 触发
- 膝盖动作禁忌：限制深蹲深度、避免开链膝伸展、避免高冲击落地
- LB A 组基准：40 码 5.1（用户 5.2，略慢但接受）、5-10-5 4.9（用户 4.8，达标）
- Spring Ankle 系统（LB 变向依赖脚踝）
- inseason 维持力量 + 比赛周降量
- 建议：看骨科/物理治疗评估未手术 ACL 当前稳定性
- 可纠正方向：加强 VMO（股内侧斜头）+ 后链 + 本体感觉

**Must not have：**
- 全蹲大重量（膝盖不适）
- 深度跳高高度（落地不稳 + ACL 旧伤）
- 忽视膝盖症状直接开训练

**Red flags：**
- 安排 Box Jump 80cm → 错（落地冲击）
- 建议 Full Depth 深蹲 1RM 测试 → 错

---

## 附录：每个 case 自检清单

跑完一个 case 后逐项打勾：

- [ ] 诊断标签（gap、phase、injury_flag）都对
- [ ] P0 优先级符合预期
- [ ] 伤病禁忌全部触发
- [ ] 动作选择符合训练年限限制
- [ ] 运动基准正确（不把篮球按橄榄球处理）
- [ ] 训练阶段逻辑正确（inseason 不加新刺激）
- [ ] 康复案例：Step 8 启动 + 分期 + 边界声明
- [ ] 新手案例：动作复杂度降级
- [ ] 青少年案例：LTAD 框架 + overuse 警告
