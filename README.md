<div align="center">

<h1><sub>Baorong Yang</sub></h1>

<p><strong>算子 Coding Agent · Skill 自进化 · AI Agent 工程化</strong></p>
<p>2027 届硕士 · 关注 AI Agent / 后端研发岗位</p>

<p>
  <a href="https://github.com/zed123214/kitagent">KitAgent</a> ·
  <a href="https://github.com/zed123214/kitagent#operator-demo">算子优化实战</a> ·
  <a href="https://github.com/zed123214/SkillGrow">SkillGrow</a> ·
  <a href="https://gitcode.com/cann/ops-math/pull/5425">CANN Contribution</a> ·
  <a href="mailto:yangbaorong78@gmail.com">Email</a>
</p>

</div>

我开发了算子优化工作台 **KitAgent** 和 Skill 评测工具 **SkillGrow**，也为昇腾 CANN 贡献了 Equal 算子。

## 代表项目

<table width="100%">
<tr>
<td width="50%" valign="top">

<h3><a href="https://github.com/zed123214/kitagent">KitAgent</a></h3>
<p><strong>面向算子开发与优化的 Coding Agent 工作台</strong></p>

</td>
<td width="50%" valign="top">

<h3><a href="https://github.com/zed123214/SkillGrow">SkillGrow</a></h3>
<p><strong>失败反馈驱动的 Skill 自进化</strong></p>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<a href="https://github.com/zed123214/kitagent#demo">
  <img src="https://raw.githubusercontent.com/zed123214/kitagent/main/docs/assets/equal-operator-overview.png" alt="KitAgent：Equal 算子实现、工具审批、精度验证与性能对比" width="480" />
</a>

</td>
<td width="50%" valign="top">

<a href="https://github.com/zed123214/SkillGrow#产品预览">
  <img src="https://raw.githubusercontent.com/zed123214/SkillGrow/main/docs/assets/dashboard-overview.png" alt="SkillGrow：用例评测、评分依据与运行追踪 Dashboard" width="480" />
</a>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<p>让 Agent 参与算子实现、测试与性能优化，在 Web 工作台中逐轮推进任务、审批工具调用并检查实验结果；同时提供 CLI 与 TUI。</p>

<ul>
  <li><strong>算子开发：</strong>整理规格与基线，修改候选实现，执行正确性测试与配对测速，汇总结果并导出报告。</li>
  <li><strong>任务恢复：</strong>在 Graph + SQLite + Local 模式下持久化检查点与审批状态，支持 Core 重启后续接任务、复用已记录的工具结果。</li>
  <li><strong>工具隔离：</strong>按会话分配 Kubernetes 沙箱，管理资源限制、网络策略与回收；接入 MCP、Skills 和子 Agent。</li>
  <li><strong>执行追踪：</strong>在工作台查看流式事件、工具时间线与审批记录，导出运行报告。</li>
</ul>

<p><strong>工程验证：</strong>单节点 kind + Cilium、离线 Provider 环境下，20 个并发会话完成 200 次跨会话读写探测，泄漏为 0；100 次沙箱创建与回收全部完成，最终资源残留为 0。</p>

</td>
<td width="50%" valign="top">

<p>SkillGrow 是我在 <strong>2026 字节跳动工程训练营</strong> 做的项目，用财报抽取的失败样例评测和改进 Skill。</p>

<ul>
  <li><strong>失败诊断：</strong>关联执行轨迹与解析结果，结合分层评测和 Judge 诊断，定位输出格式、表格结构与字段抽取问题。</li>
  <li><strong>候选修订：</strong>将失败反馈转化为 Skill 文档与规则候选补丁，通过 Schema 与路径白名单约束修改范围。</li>
  <li><strong>修改记录：</strong>在独立工作区保存候选补丁、回放评分和版本快照，方便比较每次修订的结果。</li>
  <li><strong>质量判断：</strong>通过 DocumentIR 与 Evidence Pack 组织文档和证据，输出质量决策，并按运行追踪产物与报告。</li>
</ul>

<p><strong>可运行示例：</strong>提供 20 个合成回放用例，演示文档转换、证据构建与质量判断；金融解析 Skill 使用 LAS，评测模块结合 OpenClaw。</p>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<p><sub>Python · asyncio · LangGraph · SQLite · Kubernetes · React</sub></p>
<p>
  <a href="https://github.com/zed123214/kitagent#demo">算子开发演示</a> ·
  <a href="https://github.com/zed123214/kitagent#operator-demo">优化实战</a> ·
  <a href="https://github.com/zed123214/kitagent#architecture">系统架构</a> ·
  <a href="https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md">恢复设计</a>
</p>

</td>
<td width="50%" valign="top">

<p><sub>Python · OpenClaw · LAS · Pytest · Streamlit · Docker</sub></p>
<p>
  <a href="https://github.com/zed123214/SkillGrow#产品预览">查看演示</a> ·
  <a href="https://github.com/zed123214/SkillGrow#核心能力">核心能力</a> ·
  <a href="https://github.com/zed123214/SkillGrow#工作流">自进化流程</a>
</p>

</td>
</tr>
</table>

## 算子开发与优化实践

### 昇腾 CANN · Equal 算子

为 **CANN / ops-math** 贡献 Equal 算子实现，基于 **Ascend C** 完成多维广播与多数据类型适配，**306/306 精度通过，PR 已合并**。实践覆盖广播轴压缩、Host 侧 stride 预计算、UB 分块与缓存复用，以及特殊浮点值和 INT64 比较语义。

[查看贡献与代码评审 → PR #5425](https://gitcode.com/cann/ops-math/pull/5425)

### SparseFlashAttentionGrad · 稀疏 Attention 反向优化

围绕 **dQ / dK / dV** 梯度计算，优化稀疏索引频数统计、AIC / AIV 协作与流水排程，并将查询计算和 dK / dV 归约一起纳入负载分配。

在 **910B3 五分片样机实验**中，重新分配归约任务后，正序测量 **280.17 → 258.99 μs（下降 7.56%）**，反序测量 **275.31 → 259.71 μs（下降 5.67%）**。另在 **910B4 / CANN 8.5.0** 下完成 R5 集成回归，包含 **56 份 FP16 精度报告、112 次毒值检查**。

**算子竞赛**　我在 2026 CANN 挑战赛获**决赛三等奖**，也与队友凭稀疏注意力反向算子优化方案获中国电信「星辰杯」高校 AI 算子开发挑战赛**优秀奖（决赛 16 强）**。

[查看两个算子的优化过程与实验条件 →](https://github.com/zed123214/kitagent#operator-demo)

### 在 KitAgent 中推进一轮实验

**理解规格与基线 → 分析瓶颈 → 修改候选 → 精度验证与配对测速 → 汇总报告、继续迭代。**

在同一会话里查看每一步调用了哪些工具，确认文件写入和命令执行。常用步骤可以保存为 Skills，在下次实验中复用。

[观看 Equal 开发演示](https://github.com/zed123214/kitagent#demo) · [复制算子优化任务模板](https://github.com/zed123214/kitagent#operator-demo) · [启动工作台](https://github.com/zed123214/kitagent#quick-start)

## 学术成果

我主要研究无线网络中的资源分配，目前有两篇论文在外审。

- **约束感知深度展开**（第一作者）　把迭代优化算法展开为固定层数的网络，在可靠性和速率约束下为全双工车联网分配资源。
- **图神经网络功率控制**（第三作者）　参与 DPGNN 研究，将方向先验引入图神经网络，为相互干扰的链路分配发射功率，以满足各链路的服务质量要求。

此前以第一作者发表了[车联网功率与频谱联合分配论文](https://doi.org/10.1016/j.phycom.2026.103403)，另有两篇第二作者光学论文（[喷流整形](https://doi.org/10.1016/j.optlastec.2024.111467)、[折射率传感](https://doi.org/10.1016/j.measurement.2024.115530)）。

## 社区交流

在小林coding 的[《杀进决赛！这 28 支队伍把算子优化卷疯了！》](https://mp.weixin.qq.com/s/Sr8wVJQw0Pt6xZSOtdHp2w)评论区分享了 KitAgent 算子开发工作流，获得作者点赞与读者试用反馈。欢迎一起交流算子优化方法和 Coding Agent 的开发实践。

## 开发记录

| 工作 | 实现与验证入口 |
| --- | --- |
| **KitAgent：算子 Coding Agent 工作流** | [开发演示](https://github.com/zed123214/kitagent#demo)与[优化案例](https://github.com/zed123214/kitagent#operator-demo)，串起规格分析、代码修改、正确性验证、配对测速与报告交付。 |
| **KitAgent：Web 工作台与会话权限** | [功能提交](https://github.com/zed123214/kitagent/commit/3bbcee2d62bf79c6203a459d5d5d3035c64d03ac)包含浏览器工作台、Core 网关、运行报告与权限控制，附有后端、前端和浏览器测试记录。 |
| **KitAgent：Kubernetes 沙箱** | [功能提交](https://github.com/zed123214/kitagent/commit/634ba01c983b27ffa293d658638ade6c697ffa3c)与[部署、验收说明](https://github.com/zed123214/kitagent/blob/main/docs/kubernetes-sandbox.md)，覆盖会话隔离、资源限制与回收。 |
| **KitAgent：持久化恢复设计** | [设计文档](https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md)说明检查点、工具执行记录、恢复令牌与并发恢复的处理方式。 |
| **SkillGrow：失败反馈驱动的自进化** | [候选与回归模块](https://github.com/zed123214/SkillGrow/tree/main/financial-pdf-skill-eval-framework/optimizer/)围绕失败轨迹生成规则补丁提案，管理候选工作区、回放记录与版本快照。 |
| **SkillGrow：文档质量与运行隔离** | [功能提交](https://github.com/zed123214/SkillGrow/commit/61d73ab067a6dbb2b618eb4a42d79706b829f447)包含文档表示、证据包、质量策略和回归测试。 |

[KitAgent 提交记录](https://github.com/zed123214/kitagent/commits/main/) · [SkillGrow 提交记录](https://github.com/zed123214/SkillGrow/commits/main/)

## 技术栈

| 方向 | 技术 |
| --- | --- |
| **AI 应用** | LangGraph · MCP · Skills · RAG · Milvus |
| **后端开发** | Python · asyncio · FastAPI · Java · Spring Boot · Redis |
| **工程与评测** | Docker · Kubernetes · SQLite · Pytest · GitHub Actions |
| **算子开发** | Ascend C · CANN · Tiling · AIC / AIV 协作 · 性能分析 |

---

欢迎交流 **算子 Coding Agent、Skill 自进化、Ascend C 性能优化与 Agent 工程**，也欢迎联系 **2027 届 AI Agent / 后端研发岗位**。

**Email：** [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)
