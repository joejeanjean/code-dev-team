---
name: code-dev-team
description: "代码开发团队 skill：融合 REA 逆向分析能力与 agency-agents 专家团队编排，覆盖「需求分析 → 架构设计 → 前端/后端实现 → 逆向研究 → 测试验证」闭环。当用户要开发/复刻/重构一个软件系统（尤其是含打包应用、Electron、二进制、已有产物的项目），或以 PM/架构师/前端/后端/QA 团队方式协作时使用。触发词：代码开发、开发团队、复刻系统、逆向、打包应用、Electron 分析、PM、架构师、前后端、QA、开发测试循环。"
metadata:
  xiaobangclaw:
    emoji: "🛠️"
    requires: {}
---

# 代码开发团队 skill（REA × Agency 融合版）

> 面向「从零/从现有产物 → 交付完整软件系统」的开发任务。
> **两条核心能力线**：
> 1. **Agency 团队**（角色扮演 + NEXUS 编排 + 子智能体）：需求、架构、前后端、测试。
> 2. **REA 逆向**（逆向分析已有产物）：拆解打包应用/二进制/运行时，还原行为、协议、界面。
> 两者结合的场景：**复刻/重写已有软件**（有原版产物可逆向）、**分析黑盒系统后再自研**、**联调验证**。

---

## 一、何时使用

| 场景 | 组合方式 |
|------|----------|
| 全新功能/系统（有源码仓库） | Agency 团队（源码分析走普通工具，不启用 REA 就绪检查） |
| **复刻/重写已有产品**（有 exe/asar/apk/二进制） | REA 先逆向出行为与协议 → Agency 团队按证据实现 |
| 排查「为什么它这样工作」 | REA 单独（证据优先），不卷入团队编排 |
| 联调/兼容改造 | REA 观察运行时 + Agency 角色做实现与 QA |

---

## 二、Agency 团队核心（角色库 + NEXUS 编排）

### 1. 角色库位置（本地已存在）

```
D:\code2\agency-agents-zh-main\agency-agents-zh-main\<部门>\<角色文件>.md
```

完整清单见仓库 README/CATALOG.md（按中文名搜路径）。

### 2. 用法一：单角色加载（角色切换）

read 对应角色文件 → 按 frontmatter + 人设扮演。

示例：
```
请使用 engineering/engineering-software-architect.md 这个角色来评审我的架构
→ 读取该文件，以软件架构师人设评审（DDD、架构决策、可扩展性）。
```

### 3. 用法二：组建代码开发团队（NEXUS 编排）

协作节奏由 NEXUS 策略定义（仓库 strategy\nexus-strategy.md，及 phase-playbooks\、runbooks\、activation-prompts\、handoff-templates\）。
开发任务常用：
- **NEXUS-Micro**：修 bug / 做功能（1–5 天）
- **NEXUS-Sprint**：MVP / 完整系统（2–6 周）

### 4. 核心 5 类角色（已注册为子智能体）

| 角色 | 角色文件 | 职责 |
|------|----------|------|
| 产品经理 | product\product-manager.md | 需求、PRD、验收标准、干系人对齐 |
| 后端架构师 | engineering\engineering-backend-architect.md | API 设计、数据库架构、可扩展性 |
| 前端开发者 | engineering\engineering-frontend-developer.md | React/Vue、UI 实现、性能优化 |
| 高级开发者/联调 | engineering\engineering-senior-developer.md | 高品质实现、端到端集成 |
| 测试/QA | testing\testing-evidence-collector.md + testing\testing-reality-checker.md + testing\testing-api-tester.md | 证据化测试、生产就绪验证 |

### 5. 小邦 Claw 里调动团队的两条路线

- **路线 A（单会话角色切换）**：按需读角色文件扮演，逐阶段产出并互相校验，质量门禁 = 每阶段给证据。
- **路线 B（子智能体编排）**：已注册 pm / backend / frontend / developer / qa 五个子智能体。主 Agent 用 submit_to_agent 派发、check_agent_task 轮询、把上游结果传给下游（PM→后端→前端→开发→QA）。

### 6. 代码开发角色速查（仅保留相关）

#### 工程 engineering\
前端、后端、软件架构、高级开发、AI 工程师、DevOps 自动化、安全工程师、代码审查员、快速原型、移动应用、桌面应用、数据工程、数据库优化/可靠性、平台/API 平台、Rust 重构、网络、Git 工作流、SRE、故障响应、威胁检测、智能合约、微信小程序、飞书/钉钉集成等。

#### 测试 testing\
证据收集、现实检验、API 测试、性能基准、无障碍审核、测试结果分析、测试自动化、嵌入式 QA。

#### 产品 product\
产品经理、Sprint 排序师、趋势研究员、反馈分析师、DX 工程师。

#### 项目管理 project-management\
高级项目经理、项目牧羊人、实验追踪、Jira 工作流、会议纪要。

#### 安全 security\
安全工程师/架构师、应用安全、云安全、渗透测试、代码安全审计（含 AI 生成代码）、密钥凭据、合规审计、事件响应、区块链审计。

#### 公司经营 company\（仅技术决策相关）\
CTO（技术路线/架构决策/研发组织/技术债）。

#### 专项 specialized\（仅开发相关）\
智能体编排、提示词工程、MCP 构建器、工作流架构、文档生成器、数据整合、报告分发、模型 QA、自动化治理、技术翻译等；**跳过**留学/医疗/法务/HR/ESG/房产/旅游等非开发角色。
## 三、常用开发激活模板

**修复 Bug（NEXUS-Micro）**
```
激活后端架构师，调查并修复 [BUG 描述]；
修完后激活 API 测试员验证，再激活证据收集者确认无视觉回归。
```

**做功能/MVP（NEXUS-Sprint）**
```
激活智能体编排者，NEXUS-Sprint 模式。
功能：[描述]；时间线：[目标周数]。
团队：PM=产品经理+Sprint排序师；工程=前端开发者+后端架构师+DevOps自动化师；QA=证据收集者+现实检验者+API测试员。
从第 1 阶段做架构与 Sprint 规划；所有实现任务跑开发-测试循环；上线前拿现实检验者批准。
```

**架构评审**
```
以软件架构师视角评审以下方案：[描述]，重点：边界/DDD、架构决策、可扩展性、技术债。
然后请安全工程师做一次代码安全审查（OWASP Top 10 / 硬编码密钥 / 注入）。
```

**复刻已有产品（REA 前置）**
```
先用 REA 分析目标产物（见下文），产出行为/协议/界面证据；
再按证据组建 PM→架构师→前后端→QA 团队实现；最后用 REA 运行时观察做联调验证。
```
## 四、REA 逆向分析核心（连接与目标路由）

> 源码可读则跳过本节，用普通工具。仅当结论依赖**已发布产物**（exe/asar/apk/二进制/运行时）时使用 REA。

### 1. 连接（仅在需要时）

- 若 REA MCP 工具可用且注册未过期 → **直接开始**，不做诊断。
- 工具缺失/被拦截 → 读技能 `references/connection-and-recovery.md` 诊断（区分：注册缺失 → scoped 修复；注册完好但会话无工具 → 重启重连；缺 provider → 只影响对应任务）。
- 修复用只读 dry-run 计划（`npx -y rea-agents setup --client <client> --dry-run --json`），批准后再写。
- **REA setup 从不安装/升级** Node.js、npm、Java、Ghidra、IDA、JADX、Binwalk、Unblob 等无关软件。
- CLI 兜底（无需 MCP）：`npx -y rea-agents analyze-javascript-application <path> --json`。

### 2. 目标路由（选第一个工具）

| 目标 | 工具 |
|------|------|
| ASAR / 提取的 JS/Electron 树 | `analyze_javascript_application` |
| ZIP/APK/IPA/MSIX/DMG 归档 | `open_binary`（本地路径） |
| Android APK 代码 | `inspect_android_package` |
| 托管 PE/CLI 程序集 | `inspect_managed_artifact` |
| 固件镜像 | `inspect_firmware_regions` / `extract_firmware` |
| .NET NativeAOT PE/ELF | native Ghidra 分析 |
| 用户已打开的浏览器页 | `list_browser_targets`；需操作则 `capture_browser_scenario` |
| 已打开的 Electron 运行时 | `list_electron_targets`（先查 fuses） |
| 网络抓包 HAR/SAZ/qlog | `inspect_web_network_capture` |
| SQLite 快照 | `inspect_sqlite_database` |
| Go/Rust 二进制元数据 | `inspect_go_binary` / `inspect_rust_binary` |
| ELF 布局/符号/缓解 | `inspect_binary_layout` |
| PE 资源树 | `inspect_pe_resources` |
| native 可执行文件/分析库 | `open_binary` → 聚焦分析工具 |
| WASM 产物 | `inspect_wasm_artifact` |

> 用户只说 "my app" 而无名无路径 → 先问清目标；不替用户选示例应用。
### 3. 证据优先的工作方式

- **Summary-first**：大目标先 `detail:"summary"`，再用 `inspect_analysis_view` 分页取详情；不重复相同分析。
- **Evidence 贯穿**：每条结论标注"观察/推断/未知"，引用 Evidence ID；不把静态分析当运行时观察。
- **先检查清单**：多子系统问题先列「问题→所需证据」，再逐条查、批量假设、按需扩展。
- **知情复用**：先看已有 session/database/bookmarks；不做重复分析。
- **收尾**：复盘清单，每个问题标记 已答/部分/未答，结论与证据 ID 绑定，关闭已打开的 native session（`close_binary`）。

### 4. 只读相关指南

- NATIVE / 托管程序集 / 归档：`references/native-and-artifacts.md`
- ASAR / JS / 功能追踪 / 版本对比：`references/javascript-applications.md`
- Android：`references/android-applications.md`
- 浏览器/Electron 观察：`references/runtime-observation.md`
- 证据分页/对比/验证：`references/evidence-workflows.md`
## 五、团队协作注意事项

- 角色文件很多，**按需 read 目标角色**，别一次全读；完整清单交 CATALOG.md。
- 团队协作务必用足 **"质量门禁 + 证据"**（每阶段产出可验证证据）。
- 已注册子智能体：`pm / backend / frontend / developer / qa`；需加角色可继续同方式注册。
- **REA 与团队结合点**：逆向所得证据 = 团队需求/验收的「事实源」；QA 用 REA 运行时观察做最终验证；实现阶段不要用 REA 替代正常编码工具。

---

# 附：快速决策表（30 秒选路线）

| 要做什么 | 路线 |
|----------|------|
| 全新系统（有源码/无参照物） | Agency：PM→架构→前后端→QA |
| 复刻已有封闭产品 | REA 先出证据 → Agency 实现 → REA 验证 |
| 只想知道某产物为什么这样 | 仅 REA |
| 老系统联调/兼容 | REA 观察 + 单角色（集成开发者/QA） |
### 6. 代码开发角色速查（仅保留相关）

#### 工程 engineering\
前端、后端、软件架构、高级开发、AI 工程师、DevOps 自动化、安全工程师、代码审查员、快速原型、移动应用、桌面应用、数据工程、数据库优化/可靠性、平台/API 平台、Rust 重构、网络、Git 工作流、SRE、故障响应、威胁检测、智能合约、微信小程序、飞书/钉钉集成等。

#### 测试 testing\
证据收集、现实检验、API 测试、性能基准、无障碍审核、测试结果分析、测试自动化、嵌入式 QA。

#### 产品 product\
产品经理、Sprint 排序师、趋势研究员、反馈分析师、DX 工程师。

#### 项目管理 project-management\
高级项目经理、项目牧羊人、实验追踪、Jira 工作流、会议纪要。

#### 安全 security\
安全工程师/架构师、应用安全、云安全、渗透测试、代码安全审计（含 AI 生成代码）、密钥凭据、合规审计、事件响应、区块链审计。

#### 公司经营 company\（仅技术决策相关）\
CTO（技术路线/架构决策/研发组织/技术债）。

#### 专项 specialized\（仅开发相关）\
智能体编排、提示词工程、MCP 构建器、工作流架构、文档生成器、数据整合、报告分发、模型 QA、自动化治理、技术翻译等；**跳过**留学/医疗/法务/HR/ESG/房产/旅游等非开发角色。
## 三、常用开发激活模板

**修复 Bug（NEXUS-Micro）**
```
激活后端架构师，调查并修复 [BUG 描述]；
修完后激活 API 测试员验证，再激活证据收集者确认无视觉回归。
```

**做功能/MVP（NEXUS-Sprint）**
```
激活智能体编排者，NEXUS-Sprint 模式。
功能：[描述]；时间线：[目标周数]。
团队：PM=产品经理+Sprint排序师；工程=前端开发者+后端架构师+DevOps自动化师；QA=证据收集者+现实检验者+API测试员。
从第 1 阶段做架构与 Sprint 规划；所有实现任务跑开发-测试循环；上线前拿现实检验者批准。
```

**架构评审**
```
以软件架构师视角评审以下方案：[描述]，重点：边界/DDD、架构决策、可扩展性、技术债。
然后请安全工程师做一次代码安全审查（OWASP Top 10 / 硬编码密钥 / 注入）。
```

**复刻已有产品（REA 前置）**
```
先用 REA 分析目标产物（见下文），产出行为/协议/界面证据；
再按证据组建 PM→架构师→前后端→QA 团队实现；最后用 REA 运行时观察做联调验证。
```
## 四、REA 逆向分析核心（连接与目标路由）

> 源码可读则跳过本节，用普通工具。仅当结论依赖**已发布产物**（exe/asar/apk/二进制/运行时）时使用 REA。

### 1. 连接（仅在需要时）

- 若 REA MCP 工具可用且注册未过期 → **直接开始**，不做诊断。
- 工具缺失/被拦截 → 读技能 `references/connection-and-recovery.md` 诊断（区分：注册缺失 → scoped 修复；注册完好但会话无工具 → 重启重连；缺 provider → 只影响对应任务）。
- 修复用只读 dry-run 计划（`npx -y rea-agents setup --client <client> --dry-run --json`），批准后再写。
- **REA setup 从不安装/升级** Node.js、npm、Java、Ghidra、IDA、JADX、Binwalk、Unblob 等无关软件。
- CLI 兜底（无需 MCP）：`npx -y rea-agents analyze-javascript-application <path> --json`。

### 2. 目标路由（选第一个工具）

| 目标 | 工具 |
|------|------|
| ASAR / 提取的 JS/Electron 树 | `analyze_javascript_application` |
| ZIP/APK/IPA/MSIX/DMG 归档 | `open_binary`（本地路径） |
| Android APK 代码 | `inspect_android_package` |
| 托管 PE/CLI 程序集 | `inspect_managed_artifact` |
| 固件镜像 | `inspect_firmware_regions` / `extract_firmware` |
| .NET NativeAOT PE/ELF | native Ghidra 分析 |
| 用户已打开的浏览器页 | `list_browser_targets`；需操作则 `capture_browser_scenario` |
| 已打开的 Electron 运行时 | `list_electron_targets`（先查 fuses） |
| 网络抓包 HAR/SAZ/qlog | `inspect_web_network_capture` |
| SQLite 快照 | `inspect_sqlite_database` |
| Go/Rust 二进制元数据 | `inspect_go_binary` / `inspect_rust_binary` |
| ELF 布局/符号/缓解 | `inspect_binary_layout` |
| PE 资源树 | `inspect_pe_resources` |
| native 可执行文件/分析库 | `open_binary` → 聚焦分析工具 |
| WASM 产物 | `inspect_wasm_artifact` |

> 用户只说 "my app" 而无名无路径 → 先问清目标；不替用户选示例应用。
### 3. 证据优先的工作方式

- **Summary-first**：大目标先 `detail:"summary"`，再用 `inspect_analysis_view` 分页取详情；不重复相同分析。
- **Evidence 贯穿**：每条结论标注"观察/推断/未知"，引用 Evidence ID；不把静态分析当运行时观察。
- **先检查清单**：多子系统问题先列「问题→所需证据」，再逐条查、批量假设、按需扩展。
- **知情复用**：先看已有 session/database/bookmarks；不做重复分析。
- **收尾**：复盘清单，每个问题标记 已答/部分/未答，结论与证据 ID 绑定，关闭已打开的 native session（`close_binary`）。

### 4. 只读相关指南

- NATIVE / 托管程序集 / 归档：`references/native-and-artifacts.md`
- ASAR / JS / 功能追踪 / 版本对比：`references/javascript-applications.md`
- Android：`references/android-applications.md`
- 浏览器/Electron 观察：`references/runtime-observation.md`
- 证据分页/对比/验证：`references/evidence-workflows.md`
## 五、团队协作注意事项

- 角色文件很多，**按需 read 目标角色**，别一次全读；完整清单交 CATALOG.md。
- 团队协作务必用足 **"质量门禁 + 证据"**（每阶段产出可验证证据）。
- 已注册子智能体：`pm / backend / frontend / developer / qa`；需加角色可继续同方式注册。
- **REA 与团队结合点**：逆向所得证据 = 团队需求/验收的「事实源」；QA 用 REA 运行时观察做最终验证；实现阶段不要用 REA 替代正常编码工具。

---

# 附：快速决策表（30 秒选路线）

| 要做什么 | 路线 |
|----------|------|
| 全新系统（有源码/无参照物） | Agency：PM→架构→前后端→QA |
| 复刻已有封闭产品 | REA 先出证据 → Agency 实现 → REA 验证 |
| 只想知道某产物为什么这样 | 仅 REA |
| 老系统联调/兼容 | REA 观察 + 单角色（集成开发者/QA） |
