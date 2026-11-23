# 杨宝荣 · Baorong Yang

[学术主页](https://zed123214.github.io/)

天津师范大学 · 智能科学与技术硕士研究生 · 预计 2027 年 6 月毕业

我研究车联网中的功率与频谱分配，关注怎样在满足链路可靠性约束的同时，降低资源分配的求解成本。我也用 Ascend C 开发昇腾算子，并在 KitAgent 中把算子修改、精度验证和配对测速串成可回放的实验。

[Google Scholar](https://scholar.google.com/citations?user=WuxKoZIAAAAJ&hl=zh-CN) · [第一作者论文](https://doi.org/10.1016/j.phycom.2026.103403) · [KitAgent 演示](https://github.com/zed123214/kitagent#demo) · [CANN 合入 PR](https://gitcode.com/cann/ops-math/pull/5425) · [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)

## 学术论文

### 代表作

**Joint power and spectrum allocation for bidirectional full-duplex V2V communications underlaying cellular V2I uplinks**<br>
**Baorong Yang**, Tingting Lu, Liang Han<br>
*Physical Communication*, vol. 80, 103403 (2026) · 第一作者 · [DOI](https://doi.org/10.1016/j.phycom.2026.103403)

一对车辆复用蜂窝上行频谱进行双向通信时，两个方向的可靠性要求共同限制发射功率。我们把这两个约束化为显式功率上界，逐对筛选可行的复用方案，再以交替优化得到的容量为权重做一对一匹配。在论文考察的准静态高速公路场景中，全双工方案的蜂窝上行总遍历容量高于半双工基线。

### 合作论文

**Performance Analysis of RIS-Assisted Two-Way Communication in Rician Fading Channels**<br>
Wenrui Yang, **Baorong Yang**, Liang Han<br>
*ICCEAI 2025* · 第二作者 · [官方会议日程](https://icceai.cn/2025/Program.pdf)

**A new method of Terajet shaping by hollow reflection screen**<br>
Yu-Jing Yang, **Bao-Rong Yang**, De-Long Zhang, Ning Yuan<br>
*Optics & Laser Technology*, vol. 180, 111467 (2025) · 第二作者 · [DOI](https://doi.org/10.1016/j.optlastec.2024.111467)

**Large-range refractive index sensor based on photonic jet**<br>
Yu-Jing Yang, **Bao-Rong Yang**, Meng-Qing Yuan, De-Long Zhang, Ning Yuan, Sai-Dong Xue<br>
*Measurement*, vol. 239, 115530 (2025) · 第二作者 · [DOI](https://doi.org/10.1016/j.measurement.2024.115530)

## 在审工作

**约束感知深度展开 · 第一作者**<br>
在全双工车联网的资源分配中，逐对求解发射功率是匹配前反复执行的一步。我们将功率更新展开为固定层数的网络，通过解析投影限制输出，再按物理模型剔除不可行的配对。在独立留出的 4,096 个交替优化可行样本上，按 4 个训练种子取均值，最终筛选前的速率约束违规率为 **1.422%**，投影 MLP 基线为 **10.132%**。[项目仓库](https://github.com/zed123214/constraint-aware-du-fd-v2v)

**方向先验引导的图神经网络功率控制（DPGNN）· 第三作者**<br>
这项合作研究将链路间干扰的方向性引入图神经网络，在各链路的服务质量约束下联合分配发射功率。

## 开源工程

### 昇腾 CANN 与 KitAgent

我用 Ascend C 实现了逐元素比较算子 `Equal`，负责 Host 侧分块和 AICore 计算内核，支持 1–8 维广播。实现已合入 CANN 的 `ops-math` 仓库。[合入记录 · PR #5425](https://gitcode.com/cann/ops-math/pull/5425)

**Agent 改完算子，怎么知道它算对了、跑快了？** 我把这个问题做成了 KitAgent 的一个可回放实验。以 `Equal` 为例，先用广播输入和特殊值定义预期输出，再将候选实现与参考结果逐项比较，最后对基线和候选实现做配对测速。工作台保留代码差异、工具调用和测试结果。离线演示使用脚本化模型响应，工具在本地实际执行。[Equal 开发演示](https://github.com/zed123214/kitagent#demo)

为让中断的实验可以接续，KitAgent 在 Graph + SQLite + Local 模式下保存检查点、审批状态和工具结果。在单节点 kind + Cilium 的离线验收中，20 个并发会话完成了 200 次跨会话读写探测，均未发现泄漏。[恢复设计](https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md) · [沙箱验收](https://github.com/zed123214/kitagent/blob/main/docs/kubernetes-sandbox.md)

### SkillGrow · 财报抽取评测

财报抽取结果即使符合格式，也可能把某一年的数值配到另一年的表头。我在字节跳动工程训练营开发了 SkillGrow，把字段、原文证据和逐项评分关联到同一用例。修改抽取规则后，可在独立工作区回放失败用例和此前通过的用例，检查修订效果。公开仓库提供 20 个合成回放用例。[项目与演示](https://github.com/zed123214/SkillGrow) · [候选补丁与回归评测](https://github.com/zed123214/SkillGrow/tree/main/financial-pdf-skill-eval-framework/optimizer)

## 算子竞赛

- **中国电信「星辰杯」高校 AI 算子开发挑战赛 · 决赛 16 强，优秀奖。** 我和队友优化稀疏注意力反向算子 `SparseFlashAttentionGrad`，按查询计算量和梯度归约工作量重新分配任务。在昇腾 910B3 五分片实验中，相对初版分片方案，正序、反序两轮配对测速的耗时分别降低 **7.56%** 和 **5.67%**。[实现与测速记录](https://github.com/zed123214/kitagent#operator-demo)
- **2026 CANN 挑战赛 · 决赛三等奖。** 为视频生成实现变长三维旋转位置编码算子 `VarLenNdRotaryPosEmb`，在不同注意力头之间复用旋转系数。69 组回归输入的输出均通过与 PyTorch 参考实现的容差校验。
