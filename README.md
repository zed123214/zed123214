<div align="center">

<h1>杨宝荣 <sub>Baorong Yang</sub></h1>

<p><strong>AI Agent 工程化 · 后端开发</strong></p>
<p>2027 届硕士 · 关注 AI Agent / 后端研发岗位</p>

<p>
  <a href="https://github.com/zed123214/kitagent">KitAgent</a> ·
  <a href="https://github.com/zed123214/SkillGrow">SkillGrow</a> ·
  <a href="https://gitcode.com/cann/ops-math/pull/5425">CANN Contribution</a> ·
  <a href="mailto:yangbaorong78@gmail.com">Email</a>
</p>

</div>

主要做 AI Agent 和后端开发。目前维护两个项目：**KitAgent** 是 Agent 运行时，**SkillGrow** 用来评测和改进 Agent Skill。也参与昇腾 CANN 的 Ascend C 算子开发。

## 代表项目

<!-- Keep matching sections in shared rows so unequal screenshot ratios cannot shift the project descriptions and links. -->
<table width="100%">
<tr>
<td width="50%" valign="top">

<h3><a href="https://github.com/zed123214/kitagent">KitAgent</a></h3>
<p><strong>AI Agent 运行时与可视化工作台</strong></p>

</td>
<td width="50%" valign="top">

<h3><a href="https://github.com/zed123214/SkillGrow">SkillGrow</a></h3>
<p><strong>评测驱动的 Agent Skill 迭代工作台</strong></p>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<a href="https://github.com/zed123214/kitagent#demo">
  <img src="https://raw.githubusercontent.com/zed123214/kitagent/main/docs/assets/web-workbench-overview.png" alt="KitAgent：多轮对话、工具审批与运行报告" width="480" />
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

<p>让用户通过 Web、CLI 或 TUI 提交任务、审批工具调用，并追踪执行结果。</p>

<ul>
  <li><strong>任务恢复：</strong>在 Graph + SQLite + Local 模式下持久化检查点与审批状态，支持 Core 重启后续接任务、复用已记录的工具结果。</li>
  <li><strong>工具隔离：</strong>按会话分配 Kubernetes 沙箱，管理资源限制、网络策略与回收；接入 MCP、Skills 和子 Agent。</li>
  <li><strong>执行追踪：</strong>在工作台查看流式事件、工具时间线与审批记录，导出运行报告。</li>
</ul>

<p><strong>工程验证：</strong>单节点 kind + Cilium、离线 Provider 环境下，20 个并发会话完成 200 次跨会话读写探测，泄漏为 0；100 次沙箱创建与回收全部完成，最终资源残留为 0。</p>

</td>
<td width="50%" valign="top">

<p>以金融 PDF 解析为首个场景，用评测结果定位 Skill 的失败原因，管理候选修改与回归记录。</p>

<ul>
  <li><strong>分层评测：</strong>检查输出格式、表格结构、人工标注准确率与 Judge 诊断，查看用例评分和失败阶段。</li>
  <li><strong>候选管理：</strong>根据失败记录生成规则模板补丁，在独立工作区管理候选，保存产物回放评分与回归记录。</li>
  <li><strong>质量判断：</strong>通过 DocumentIR 与 Evidence Pack 组织文档和证据，输出质量决策，并按运行追踪产物与报告。</li>
</ul>

<p><strong>可运行示例：</strong>提供 20 个合成回放用例，演示文档转换、证据构建与质量判断；金融解析 Skill 使用 LAS，评测模块结合 OpenClaw。</p>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<p><sub>Python · asyncio · LangGraph · SQLite · Kubernetes · React</sub></p>
<p>
  <a href="https://github.com/zed123214/kitagent#demo">查看演示</a> ·
  <a href="https://github.com/zed123214/kitagent#architecture">系统架构</a> ·
  <a href="https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md">恢复设计</a>
</p>

</td>
<td width="50%" valign="top">

<p><sub>Python · OpenClaw · LAS · Pytest · Streamlit · Docker</sub></p>
<p>
  <a href="https://github.com/zed123214/SkillGrow#产品预览">查看演示</a> ·
  <a href="https://github.com/zed123214/SkillGrow#核心能力">核心能力</a> ·
  <a href="https://github.com/zed123214/SkillGrow#工作流">迭代流程</a>
</p>

</td>
</tr>
</table>

## 开源贡献

### 昇腾 CANN · Equal 算子

为 **CANN / ops-math** 贡献 Equal 算子实现，基于 **Ascend C** 完成多维广播与多数据类型适配，**PR 已合并**。

[查看贡献与代码评审 → PR #5425](https://gitcode.com/cann/ops-math/pull/5425)

## 开发记录

以下记录包含具体实现、验证说明和设计取舍，便于从主页继续查看代码。

| 工作 | 实现与验证入口 |
| --- | --- |
| **KitAgent：Web 工作台与会话权限** | [功能提交](https://github.com/zed123214/kitagent/commit/3bbcee2d62bf79c6203a459d5d5d3035c64d03ac)包含浏览器工作台、Core 网关、运行报告与权限控制，提交说明记录了离线 Python、前端状态和浏览器测试。 |
| **KitAgent：Kubernetes 沙箱** | [功能提交](https://github.com/zed123214/kitagent/commit/634ba01c983b27ffa293d658638ade6c697ffa3c)与[部署、验收说明](https://github.com/zed123214/kitagent/blob/main/docs/kubernetes-sandbox.md)，覆盖会话隔离、资源限制与回收。 |
| **KitAgent：持久化恢复设计** | [设计文档](https://github.com/zed123214/kitagent/blob/main/docs/durable-recovery.md)说明检查点、工具执行记录、恢复令牌与并发恢复的处理方式。 |
| **SkillGrow：文档质量与运行隔离** | [功能提交](https://github.com/zed123214/SkillGrow/commit/61d73ab067a6dbb2b618eb4a42d79706b829f447)包含文档表示、证据包、质量策略和回归测试，并记录专项验证结果及当时全量离线测试的已知失败。 |

[KitAgent 提交记录](https://github.com/zed123214/kitagent/commits/main/) · [SkillGrow 提交记录](https://github.com/zed123214/SkillGrow/commits/main/)

## 技术栈

| 方向 | 技术 |
| --- | --- |
| **AI 应用** | LangGraph · MCP · Skills · RAG · Milvus |
| **后端开发** | Python · asyncio · FastAPI · Java · Spring Boot · Redis |
| **工程与评测** | Docker · Kubernetes · SQLite · Pytest · GitHub Actions |
| **算子开发** | Ascend C · CANN |

---

欢迎交流 **Agent 运行时、工具集成与评测工程**，也欢迎联系 **2027 届 AI Agent / 后端研发岗位**。

**Email：** [yangbaorong78@gmail.com](mailto:yangbaorong78@gmail.com)
