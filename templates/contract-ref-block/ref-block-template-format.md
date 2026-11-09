<!-- ── Schema-As-Code 交付件元数据 ──
artifact_id:      TPL-REFBLOCK-v1.0.0
artifact_type:    模版库·契约引用块（Prompt 前缀的载体形态）
applicable_products: 全部（凡使用 AGENTS.md / CLAUDE.md / Skill 文件的项目）
output_type:      Prompt 前缀的载体形态（打进文档级指令载体的文件格式）
mapped_patterns:  随引用契约继承（ERR / PRO / BND / ACT / ALR / INF）
track_theme:      ⑨ 约束显化（载体对接）
source_article:   https://www.yuque.com/u222739/why7ts/qs676o6ufefqr6zu -->

<!-- schema-as-code:contract-ref
     contract_id: <契约ID>
     version: <版本号>
     source: 契约库 · 编译管线自动生成，禁止手改
     check: 对账系统按 contract_id + version 校验时效 -->
## 语义约束（契约引用 · <契约名>）

本仓库的界面生成代码受契约 <contract_id> <version> 约束：
- <必须型条款：本场景必须表达什么语义>
- <禁止型条款：本场景禁止的表达/绑定>
- <限制型条款：只能使用的枚举值或范围>

完整条款以契约库当前版本为准。本引用块由编译管线随契约版本自动更新，
手改将在同步对账时被标记。
