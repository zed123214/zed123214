# 杨宝荣 · Baorong Yang

**AI Infra · 昇腾 CANN 算子 · Coding Agent**  
天津师范大学智能科学与技术硕士生，2027 届。我用 Ascend C 开发和优化算子，也开发了 [KitAgent](https://github.com/zed123214/kitagent)，让每次算子修改都能对照参考实现检查精度、对照基线测量耗时。

## 昇腾算子

- **SparseFlashAttentionGrad · 稀疏注意力反向传播**　我和队友发现，处理较少查询行的核反而最后完成，因为这些核还承担了集中的 `dK / dV` 归约。重新分配归约任务后，在昇腾 910B3 五分片实验中，相比同轮基线，正序、反序配对测速的耗时分别下降 **7.56% 和 5.67%**。团队获星辰杯决赛 16 强、优秀奖。[分片示意与板端实测](https://github.com/zed123214/kitagent#five-tiling-demo)
- **VarLenNdRotaryPosEmb · 变长三维旋转位置编码**　为视频生成实现变长序列的三维旋转位置编码，在多个注意力头之间复用旋转系数。**69 组回归用例**全部通过与 PyTorch 参考实现的容差校验，获 **2026 年 CANN 挑战赛决赛三等奖**。
- **Equal**　实现支持 1–8 维广播的张量比较算子，已合入昇腾 CANN 官方算子库。[合入 PR #5425](https://gitcode.com/cann/ops-math/pull/5425)

## 开源项目

### [KitAgent](https://github.com/zed123214/kitagent) · 面向算子开发的 Coding Agent 运行时

工作台把代码差异、精度用例和配对测速结果放在同一次运行里。以 `SparseFlashAttentionGrad` 为例，KitAgent 可回放两轮板端实测记录。初次分片在两种测量顺序下都变慢，候选退回迭代。调整归约后，两种顺序都变快，候选进入人工审核。[候选筛选流程](https://github.com/zed123214/kitagent#operator-workflow) · [本地工具执行演示](https://github.com/zed123214/kitagent#demo)

在 Graph + SQLite + Local 模式下，任务中断后可从检查点恢复审批状态和工具结果。并发会话各自使用 Kubernetes 沙箱。在单节点 kind + Cilium 离线验收中，20 个并发会话完成 200 次跨会话读写探测，均未发现泄漏。[恢复设计](https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md) · [沙箱验收](https://github.com/zed123214/kitagent/blob/main/docs/kubernetes-sandbox.md)

### [SkillGrow](https://github.com/zed123214/SkillGrow) · 用失败样例改进 Skill

财报里的金额可能抽对了，却被配到上一年的表头。我在字节跳动工程训练营开发了 SkillGrow，把抽取字段、原文证据和逐项评分放在同一个用例里。修订规则后，在独立工作区回放失败用例和原先通过的用例，检查修复是否引入回归。仓库提供 20 个合成回放用例。[评测工作台](https://github.com/zed123214/SkillGrow#产品预览) · [补丁与回归评测](https://github.com/zed123214/SkillGrow/tree/main/financial-pdf-skill-eval-framework/optimizer)

## 研究

我研究基于深度学习的车联网功率控制，并在 [*Physical Communication*](https://doi.org/10.1016/j.phycom.2026.103403) 以第一作者发表了功率与频谱联合分配论文。

## 联系方式

欢迎交流 AI Infra 与 Coding Agent 方向的研发岗位。

[学术主页](https://zed123214.github.io/) · [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)
