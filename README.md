# 杨宝荣 · Baorong Yang

天津师范大学智能科学与技术硕士研究生，预计 2027 年毕业。

我研究车联网中的无线资源分配，关注多条链路共享频谱时如何分配发射功率。关于全双工车联网功率与频谱联合分配的工作，以第一作者发表于 [*Physical Communication*](https://doi.org/10.1016/j.phycom.2026.103403)。

我的开源工作集中在 **AI Infra 与 Coding Agent**。我用 Ascend C 实现的张量比较算子 `Equal` 已[合入昇腾 CANN](https://gitcode.com/cann/ops-math/pull/5425)。围绕算子开发，我做了 KitAgent，把代码修改、精度校验和性能对比放进同一个工作台。

## 代表项目

### [KitAgent](https://github.com/zed123214/kitagent) · 算子开发工作台

在 `Equal` 离线演示里，模型响应由脚本驱动，工具在本地实际执行。打开工作台可以看到候选实现改了哪几行、哪些广播用例通过了，以及基线和候选实现的配对测速结果。[观看 Equal 演示](https://github.com/zed123214/kitagent#demo)

为了在任务中断后接着跑，我在 Graph + SQLite + Local 模式下保存检查点、审批状态和工具结果。对并发会话，工作台按会话分配 Kubernetes 沙箱。在单节点 kind + Cilium 的离线验收中，20 个并发会话完成了 200 次跨会话读写探测，均未发现泄漏。[恢复设计](https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md) · [沙箱验收](https://github.com/zed123214/kitagent/blob/main/docs/kubernetes-sandbox.md)

### [SkillGrow](https://github.com/zed123214/SkillGrow) · 用失败样例改进 Skill

财报里的金额可能抽对了，却被配到上一年的表头。我在字节跳动工程训练营开发了 SkillGrow，把抽取字段、原文证据和逐项评分放在同一个用例里。修订规则后，在独立工作区回放失败用例和原先通过的用例，检查修复是否引入回归。仓库提供 20 个合成回放用例。[评测工作台](https://github.com/zed123214/SkillGrow#产品预览) · [补丁与回归评测](https://github.com/zed123214/SkillGrow/tree/main/financial-pdf-skill-eval-framework/optimizer)

## 算子实现与性能验证

- **CANN · Equal**　用 Ascend C 实现逐元素比较，负责 Host 侧分块和 AICore 计算内核，支持 1–8 维广播。代码已合入官方 `ops-math` 仓库。[合入 PR #5425](https://gitcode.com/cann/ops-math/pull/5425)
- **星辰杯 · 稀疏注意力反向算子**　我和队友按查询计算量和梯度归约工作量重新分配任务。在昇腾 910B3 五分片实验中，相对初版方案，正序、反序两轮配对测速耗时分别降低 **7.56%** 和 **5.67%**，团队获决赛 16 强、优秀奖。[实现与测速记录](https://github.com/zed123214/kitagent#operator-demo)
- **CANN 挑战赛 · 变长三维旋转位置编码**　为视频生成实现 `VarLenNdRotaryPosEmb`，在不同注意力头之间复用旋转系数。69 组回归输入均通过与 PyTorch 参考实现的容差校验，获 2026 年决赛三等奖。

## 联系方式

欢迎交流 AI Infra 与 Coding Agent 方向的研发岗位。

[学术主页](https://zed123214.github.io/) · [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)
