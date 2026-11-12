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

我关注 **Coding Agent 如何参与真实的算子开发与性能优化**：从理解规格、阅读代码，到修改实现、验证精度、对比性能，再根据实验结果继续迭代。

目前维护 **KitAgent**，为这套开发流程提供 Agent 运行时与可视化工作台；维护 **SkillGrow**，构建**失败反馈驱动的 Skill 自进化流程**，将失败轨迹转化为 Skill 文档与规则候选补丁，沉淀回放记录与版本快照。同时参与昇腾 CANN 的 **Ascend C** 算子开发，将广播、数据搬运、核间协作与负载均衡的实践整理为可复盘的案例。

## 代表项目

<!-- Keep matching sections in shared rows so unequal screenshot ratios cannot shift the project descriptions and links. -->
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

<p>以金融 PDF 抽取为首个场景，构建<strong>失败轨迹 → 问题诊断 → 候选修订 → 回放验证与版本沉淀</strong>的 Skill 自进化流程。</p>

<ul>
  <li><strong>失败诊断：</strong>关联执行轨迹与解析结果，结合分层评测和 Judge 诊断，定位输出格式、表格结构与字段抽取问题。</li>
  <li><strong>候选修订：</strong>将失败反馈转化为 Skill 文档与规则候选补丁，通过 Schema 与路径白名单约束修改范围。</li>
  <li><strong>迭代沉淀：</strong>在独立工作区保存候选补丁、产物回放评分、回归记录与版本快照，为下一轮 Skill 修订提供可追溯依据。</li>
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

[查看两个算子的优化过程与实验条件 →](https://github.com/zed123214/kitagent#operator-demo)

### 在 KitAgent 中推进一轮实验

**理解规格与基线 → 分析瓶颈 → 修改候选 → 精度验证与配对测速 → 汇总报告、继续迭代。**

用同一会话保留任务上下文，通过工具时间线查看执行证据，通过审批卡控制写入与命令执行；将成熟步骤整理为 Skills，复用于下一次开发。

[观看 Equal 开发演示](https://github.com/zed123214/kitagent#demo) · [复制算子优化任务模板](https://github.com/zed123214/kitagent#operator-demo) · [启动工作台](https://github.com/zed123214/kitagent#quick-start)

## 社区交流

在小林coding 的[《杀进决赛！这 28 支队伍把算子优化卷疯了！》](https://mp.weixin.qq.com/s/Sr8wVJQw0Pt6xZSOtdHp2w)评论区分享了 KitAgent 算子开发工作流，获得作者点赞与读者试用反馈。欢迎一起交流算子优化方法和 Coding Agent 的开发实践。

## 开发记录

以下记录包含具体实现、验证说明和设计取舍，便于从主页继续查看代码。

| 工作 | 实现与验证入口 |
| --- | --- |
| **KitAgent：算子 Coding Agent 工作流** | [开发演示](https://github.com/zed123214/kitagent#demo)与[优化案例](https://github.com/zed123214/kitagent#operator-demo)，串起规格分析、代码修改、正确性验证、配对测速与报告交付。 |
| **KitAgent：Web 工作台与会话权限** | [功能提交](https://github.com/zed123214/kitagent/commit/3bbcee2d62bf79c6203a459d5d5d3035c64d03ac)包含浏览器工作台、Core 网关、运行报告与权限控制，提交说明记录了离线 Python、前端状态和浏览器测试。 |
| **KitAgent：Kubernetes 沙箱** | [功能提交](https://github.com/zed123214/kitagent/commit/634ba01c983b27ffa293d658638ade6c697ffa3c)与[部署、验收说明](https://github.com/zed123214/kitagent/blob/main/docs/kubernetes-sandbox.md)，覆盖会话隔离、资源限制与回收。 |
| **KitAgent：持久化恢复设计** | [设计文档](https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md)说明检查点、工具执行记录、恢复令牌与并发恢复的处理方式。 |
| **SkillGrow：失败反馈驱动的自进化** | [候选与回归模块](https://github.com/zed123214/SkillGrow/tree/main/financial-pdf-skill-eval-framework/optimizer/)围绕失败轨迹生成规则补丁提案，管理候选工作区、回放记录与版本快照。 |
| **SkillGrow：文档质量与运行隔离** | [功能提交](https://github.com/zed123214/SkillGrow/commit/61d73ab067a6dbb2b618eb4a42d79706b829f447)包含文档表示、证据包、质量策略和回归测试，并记录专项验证结果及当时全量离线测试的已知失败。 |

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
