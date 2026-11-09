# schema-as-code-delivery

> Schema-As-Code 的消费侧交付件仓。**不问方法论，复制即交付。**
> 方法论与信源（模式库、契约库、验证机制）见生产侧主仓 [semantic-pipeline](https://github.com/2436041978-ops/semantic-pipeline)；完整论证见[语雀系列文章](https://www.yuque.com/u222739/lxcrw1)。

[![LICENSE](https://img.shields.io/badge/LICENSE-MIT-264653?style=flat-square&logo=open-source-initiative&logoColor=white)](LICENSE)
[![GITHUB](https://img.shields.io/github/stars/2436041978-ops/schema-as-code-delivery?style=flat-square&logo=github&label=GITHUB)](https://github.com/2436041978-ops/schema-as-code-delivery)

---

## 两仓分工

```
semantic-pipeline（生产侧）              schema-as-code-delivery（消费侧）
模式库 · 契约库 · 验证机制    ──────→    模版库 · 工具仓
"规则从哪来、写得对不对"                 "我能直接用什么"
```

本仓不产生新内容：所有交付件都是主仓契约与模式的**编译产物的分发形态**，每个交付件头部带信源版本号，改动一律回契约源头。

---

## 快速上手（按角色选入口）

| 你是 | 你的动作 | 入口 |
|---|---|---|
| **设计师与产品经理** | 把"我觉得不对"变成第一条 6 字段快照，提交给具备翻译能力的协作者 | [templates/snapshot-6field](templates/snapshot-6field) |
| **设计系统负责人** | 把快照翻译成第一条 7 字段 YAML 契约，起草与评审同一把尺子 | [templates/contract-7field](templates/contract-7field) |
| **前端 / AI 工程师** | 把契约引用块粘进仓库根目录的 AGENTS.md / CLAUDE.md，十分钟接入 | [templates/contract-ref-block](templates/contract-ref-block) |
| **DesignOps** | 用走查清单核对告警文案的语义分级，发布前把住措辞关 | [skills/cloudq-alert-severity-semantics](skills/cloudq-alert-severity-semantics)（走查清单在 `assets/`） |

每条路的完整指导在各交付件目录的 README 说明卡——说明卡只回答操作问题，动机与设计理由回链语雀文章。

---

## 交付件索引（四轴）

| 交付件 | AI 产品 | 编译产物类型 | 映射模式 | 主题行载体 |
|---|---|---|---|---|
| [快照模板（6 字段）](templates/snapshot-6field) | 全品类 AI 生成界面 | Guard 阶段输入（快照 JSON） | ERR / PRO / BND / ACT / ALR / INF | ⑥ 快照与模式诊断 |
| [契约模板（7 字段）](templates/contract-7field) | 全品类（填写者收敛范围） | 契约本体（四种编译产物的信源） | 随 intent_id 关联的模式 | ④⑤ |
| [契约引用块](templates/contract-ref-block) | 凡使用 AGENTS.md / CLAUDE.md / Skill 的项目 | Prompt 前缀的载体形态 | 随引用契约继承 | ⑨ 约束显化 |
| [CloudQ 告警语义分级 Skill](skills/cloudq-alert-severity-semantics) | AIOps 运维告警 | SKILL.md（载体形态） | ERR-001 + ALR-001 | 场景适配变体 |

**入库节奏**：交付件跟随主线主题行发布入库——主题行⑥补模式卡片与诊断报告模板，⑦补对抗用例集，⑧补三层读数表与消费对账表，⑨补约束意图模板与保真检查项。仓里只放已发布主题行的交付件，文章是"为什么"，交付件是"拿来用"。

---

## 交付件目录

```
schema-as-code-delivery/
├── templates/                       # 模版库（复制即用的交付件）
│   ├── snapshot-6field/             # 语义快照模板（6 字段，冻结 v1.0.0）
│   ├── contract-7field/             # YAML 契约模板（7 字段，冻结 v1.0.0）
│   └── contract-ref-block/          # 契约引用块（载体对接）
├── skills/                          # 工具仓（CloudQ / 编码工具可调用的 Skill 目录）
│   └── cloudq-alert-severity-semantics/
├── CHANGELOG.md                     # 交付件换版记录（契约升级 → 交付件换版）
└── README.md
```

每个交付件目录的固定结构：**模板本体 + 完整示例 + README 说明卡**（工具仓为 SKILL.md 目录 + 说明卡）。

---

## 更新纪律

1. **交付件是编译产物，不是文档。** 要改约束，改契约，走评审——交付件随信源版本重编译，不手改。
2. **措辞严格程度与契约一致。** "禁止"在任何交付件里不允许写成"建议"——措辞弱化是最隐蔽的分叉。
3. **版本跟随信源。** 契约 MINOR 升，交付件跟着 MINOR；每次换版记入 CHANGELOG.md。

## 许可证

MIT
