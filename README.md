<div align="center">

<h1>杨宝荣 <sub>Baorong Yang</sub></h1>

<p><strong>AI Agent 工程化 · 后端开发 · Ascend C 算子开发</strong></p>
<p>2027 届硕士 · Python / Java</p>

<p>
  <a href="https://github.com/zed123214/kitagent">KitAgent</a> ·
  <a href="https://github.com/zed123214/SkillGrow">SkillGrow</a> ·
  <a href="https://gitcode.com/cann/ops-math/pull/5425">CANN Contribution</a> ·
  <a href="mailto:yangbaorong78@gmail.com">Email</a>
</p>

</div>

我关注 **AI Agent 的执行、评测与工具集成**：构建支持多端交互、任务恢复和容器沙箱的 Agent 运行时，围绕评测反馈与候选修改迭代 Agent Skill，也参与昇腾 CANN 的 Ascend C 算子开发。

## Selected Projects

<table width="100%">
<tr>
<td width="50%" valign="top">

<h3><a href="https://github.com/zed123214/kitagent">KitAgent</a></h3>
<p><strong>AI Agent 运行时与可视化工作台</strong></p>

<a href="https://github.com/zed123214/kitagent#demo">
  <img src="https://raw.githubusercontent.com/zed123214/kitagent/main/docs/assets/web-workbench-overview.png" alt="KitAgent：多轮对话、工具审批与运行报告" width="480" />
</a>

<p>将模型调用、工具执行与会话状态组织成常驻运行时，通过 Web、CLI 和 TUI 完成任务。</p>

<ul>
  <li><strong>执行与恢复：</strong>Loop / LangGraph 双引擎，SQLite 检查点、持久化审批与工具执行日志。</li>
  <li><strong>工具与环境：</strong>MCP、Skills、子 Agent，以及按会话分配的 Kubernetes 沙箱。</li>
  <li><strong>交互与观测：</strong>流式事件、工具时间线、会话权限与运行报告。</li>
</ul>

<p><strong>工程验证：</strong>完成 20 会话并发隔离测试与 100 次沙箱创建、回收验证。</p>

<p><sub>Python · asyncio · LangGraph · SQLite · Kubernetes · React</sub></p>
<p>
  <a href="https://github.com/zed123214/kitagent#demo">查看演示</a> ·
  <a href="https://github.com/zed123214/kitagent#architecture">系统架构</a> ·
  <a href="https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md">恢复设计</a>
</p>

</td>
<td width="50%" valign="top">

<h3><a href="https://github.com/zed123214/SkillGrow">SkillGrow</a></h3>
<p><strong>评测驱动的 Agent Skill 迭代工作台</strong></p>

<a href="https://github.com/zed123214/SkillGrow#产品预览">
  <img src="https://raw.githubusercontent.com/zed123214/SkillGrow/main/docs/assets/dashboard-overview.png" alt="SkillGrow：用例评测、评分依据与运行追踪 Dashboard" width="480" />
</a>

<p>围绕任务用例、评测反馈与候选版本组织 Skill 迭代，在工作台中检查质量、诊断失败与管理修改。</p>

<ul>
  <li><strong>评测与诊断：</strong>四层评测、人工 GT、Judge 诊断与 Run Trace，定位输出质量问题。</li>
  <li><strong>候选与回归：</strong>规则模板补丁、独立候选工作区、产物回放评分与回归记录。</li>
  <li><strong>证据与交付：</strong>DocumentIR、Evidence Pack 与文档质量门控，按运行追踪产物和决策。</li>
</ul>

<p><strong>首个场景：</strong>金融 PDF 解析，结合 LAS 与 OpenClaw 实现结构化输出和分层评测。</p>

<p><sub>Python · OpenClaw · LAS · Pytest · Streamlit · Docker</sub></p>
<p>
  <a href="https://github.com/zed123214/SkillGrow#产品预览">查看演示</a> ·
  <a href="https://github.com/zed123214/SkillGrow#核心能力">核心能力</a> ·
  <a href="https://github.com/zed123214/SkillGrow#工作流">迭代流程</a>
</p>

</td>
</tr>
</table>

## Open Source Contribution

### 昇腾 CANN · Equal 算子

为 **CANN / ops-math** 贡献 Equal 算子实现，基于 **Ascend C** 完成多维广播与多数据类型适配，**PR 已合并**。

[查看贡献与代码评审 → PR #5425](https://gitcode.com/cann/ops-math/pull/5425)

## Tech Stack

| 方向 | 技术 |
| --- | --- |
| **AI 应用** | LangGraph · MCP · Skills · RAG · Milvus |
| **后端开发** | Python · asyncio · FastAPI · Java · Spring Boot · Redis |
| **工程与评测** | Docker · Kubernetes · SQLite · Pytest · GitHub Actions |
| **算子开发** | Ascend C · CANN |

---

欢迎交流 **AI Agent、RAG 应用、后端工程与算子开发**，也欢迎联系 2027 届相关岗位机会。

**Email：** [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)
