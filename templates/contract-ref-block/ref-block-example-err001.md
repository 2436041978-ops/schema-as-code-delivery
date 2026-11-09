<!-- schema-as-code:contract-ref
     contract_id: ERR-001
     version: 1.2.0
     source: 契约库 · 编译管线自动生成，禁止手改
     check: 对账系统按 contract_id + version 校验时效 -->
## 语义约束（契约引用 · ERR-001 错误状态分级）

本仓库的界面生成代码受契约 ERR-001 v1.2.0 约束：
- 错误状态必须按 error_severity 四级表达（fatal / transient / retryable / degraded），
  禁止所有错误共用同一种视觉表达；
- fatal 级状态必须以警示级视觉映射表达，文案必须包含"不可恢复"语义，
  必须提供恢复路径；禁止以"出了点小问题"等中性或降级文案表达；
- 可恢复类状态（transient / retryable）禁止使用警示级视觉映射，
  必须给出恢复预期（等待时长或重试入口）。

完整条款以契约库当前版本为准。本引用块由编译管线随契约版本自动更新，
手改将在同步对账时被标记。
