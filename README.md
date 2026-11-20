<div align="center">

<h1><sub>Baorong Yang ｜ AI Agent / 后端研发 </sub></h1>


<p>
  <a href="https://github.com/zed123214/kitagent">KitAgent</a> ·
  <a href="https://github.com/zed123214/kitagent#operator-demo">算子优化实战</a> ·
  <a href="https://github.com/zed123214/SkillGrow">SkillGrow</a> ·
  <a href="https://gitcode.com/cann/ops-math/pull/5425">CANN Contribution</a> ·
  <a href="mailto:yangbaorong78@gmail.com">Email</a>
</p>

</div>

2027 届计算机硕士,我开发了算子优化工作台 **KitAgent** 和 Skill 评测工具 **SkillGrow**，也为昇腾 CANN 贡献了 Equal 算子。

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


## 开源贡献与竞赛

- **昇腾 CANN｜开源贡献**：用 Ascend C 实现 `Equal` 逐元素比较算子，支持多维广播和多种数据类型，306 个精度用例全部通过。[ops-math PR #5425 已合并](https://gitcode.com/cann/ops-math/pull/5425)
- **2026 CANN 挑战赛｜决赛三等奖（第 14 / 4496 名）**：面向视频生成，实现变长三维旋转位置编码算子 `VarLenNdRotaryPosEmb`，以单个 kernel 支持 FP16/FP32、动态宽高和乱序时间索引。通过向量化、跨注意力头复用系数和自适应分块，官方 5 个可见测试点的耗时降低 20.9%～86.2%。在 69 组回归输入上与 PyTorch 参考实现对照，约 6885 万个输出元素均在容差内。
- **中国电信「星辰杯」高校 AI 算子开发挑战赛｜优秀奖（决赛 16 强）**：与队友优化稀疏注意力反向算子 `SparseFlashAttentionGrad`。针对 `dK`、`dV` 梯度归约集中在少数计算核、拖慢整体收尾的问题，按查询计算量和归约工作量重新分配任务。在昇腾 910B3 五分片实验中，相比初版分片方案，正序、反序两轮对照测速的耗时分别降低 7.56% 和 5.67%。

[查看 Equal 与 SparseFlashAttentionGrad 的实现、测速与回归记录 →](https://github.com/zed123214/kitagent#operator-demo)

### 在 KitAgent 中推进一轮实验

**理解规格与基线 → 分析瓶颈 → 修改候选 → 精度验证与配对测速 → 汇总报告、继续迭代。**

在同一会话里查看每一步调用了哪些工具，确认文件写入和命令执行。常用步骤可以保存为 Skills，在下次实验中复用。

[观看 Equal 开发演示](https://github.com/zed123214/kitagent#demo) · [复制算子优化任务模板](https://github.com/zed123214/kitagent#operator-demo) · [启动工作台](https://github.com/zed123214/kitagent#quick-start)

## 学术成果

研究方向为**深度学习与无线网络资源优化**，重点研究如何将迭代优化算法和链路干扰关系融入神经网络，在可靠性、速率等约束下分配功率与频谱。

**在审论文（2 篇）**
- **约束感知深度展开（第一作者）**：将迭代优化算法的更新步骤映射为固定层数的神经网络，在可靠性与速率约束下求解全双工车联网的资源分配问题。
- **图神经网络功率控制（第三作者）**：参与 DPGNN 研究，将方向先验引入图神经网络，为相互干扰的链路联合分配发射功率，以满足各链路的服务质量要求。

**已发表 SCI 论文（3 篇）**
- **第一作者（1 篇）**：研究[车联网中的功率与频谱联合分配](https://doi.org/10.1016/j.phycom.2026.103403)，发表于 *Physical Communication*。
- **第二作者（2 篇）**：[喷流整形](https://doi.org/10.1016/j.optlastec.2024.111467)发表于 *Optics & Laser Technology*；[折射率传感](https://doi.org/10.1016/j.measurement.2024.115530)发表于 *Measurement*。


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

欢迎交流 **算子 Coding Agent、Skill 自进化、Ascend C 性能优化与 Agent 工程**，也欢迎联系 **2027 届 AI Infra / 后端研发岗位**。

**Email：** [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)
