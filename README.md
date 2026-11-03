# superspec

> 自上而下业务解构与单文件 HTML 规格师 · 引导 LLM 产出人机共读的高质量 Technical Design

`superspec` 是一个面向 AI 编程智能体（Claude Code、Codex、Cursor、Alma 等）与资深架构师的规格制定标准与 Skill。它的目标不是让 LLM 机械填表或盲目粘贴代码，而是引导 LLM 像架构师一样通过「自上而下的业务解剖」推导系统生命周期，最终交付为一份具备现代文档质感、逻辑连贯、人机共读的技术方案规格书。

---

## 核心设计哲学：人类优先，AI 无歧义

1. **人类优先（Human-First）**：
   - 翻开文档的前 30 秒，先看置顶的「目标与边界」，一眼抓准“做什么 / 明确不做什么 / 职责停在哪里”。
   - 紧随流程图后给出 Guide-level 使用者心智模型叙述，帮助人类建立清晰的操作与交互直觉。
2. **AI 无歧义（AI-Unambiguous）**：
   - 沿单向时间箭头推导生命线，严禁时间倒流。
   - 每个阶段严格以「输入载荷、核心机制、阻断/降级边界、产出与状态迁移」四元组自闭环展开，为 Coding Agent 提供清晰可验证的执行轨道。
3. **主权在人（Living Spec Sovereignty）**：
   - 文档先行，以文档为核心目标；代码追随文档，而非文档追随代码。
   - Spec 修改主权仅属于人类与设计/讨论阶段。在 Coding 阶段，Coding Agent 严禁擅自修改 Spec，发现冲突或偏差仅能上报提醒，由人类拍板。

---

## 交付规范与排版美学

* **三栏现代文档结构**：左侧主导航（分组与当前项高亮）、中间正文（限宽 760px，呼吸感充沛）、右侧本页大纲（On this page，宽屏辅助定位）。
* **零外部依赖单文件 HTML**：双击即开，免构建、零 CDN，随时可落盘或归档。
* **Kami 纸面视觉体系（现代文档版）**：
  * 画布底色：暖羊皮纸 `#f5f4ed`，容器底色：象牙白 `#faf9f5`
  * 品牌色：墨水蓝 `#1B365D`，阻断报警：朱砂红 `#C23A2B`，降级提示：暖杏黄 `#8C6314`
  * 字体：现代无衬线 `PingFang SC / -apple-system`，自然字距与行高
  * 列表标记：墨水蓝克制圆点或破折号（`–`），杜绝默认大黑点
  * 杜绝浮夸卡片与带框盒子，回归纯粹的「标题 + 引导段落 + 精炼列表」
  * 流程图摒弃带圈数字，采用清晰的「阶段节点 + 淡色向下箭头（↓）」纵向串联

---

## 目录结构

```text
superspec/
├── SKILL.md                 # Agent Skill 核心规范与提示词
├── README.md                # 仓库说明文档
└── references/
    ├── template.html        # 生产级三栏 HTML 骨架模板（带标准 CSS 与 Slots）
    └── example.html         # superspec 为自身撰写的自举设计规格实例
```

---

## 安装与使用

### Alma

克隆或软链接至 Alma 配置目录：

```bash
mkdir -p ~/.config/alma/skills
ln -s /path/to/superspec ~/.config/alma/skills/superspec
```

### Claude Code / Cursor / Codex

将 `SKILL.md` 加入你的全局 rules 或项目 `.claude/skills`、`.cursorrules` 中：

```bash
# 作为独立 skill 载入
cp SKILL.md /path/to/your/project/.codex/skills/superspec/
```

当需要做 Feature 设计、写 Technical Design、架构梳理或技术方案时，直接在对话中触发：

> “使用 superspec 为 [功能名] 编写技术规格设计”

---

## License

MIT © Kayphoon
