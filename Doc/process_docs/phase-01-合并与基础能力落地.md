# Phase 01：合并与基础能力落地

## 1. 目标（Goal）
完成 `QCode.html` 与 `QCodeLink` 能力融合，形成统一入口页面 `QCodeMerged.html`，并建立可持续迭代的任务与说明文档。

## 2. 对应 Skill（Skill Mapping）
- `frontend-skill`：统一界面风格与交互骨架。
- `code-change-log`：沉淀任务变更与使用说明文档。

## 3. 实施过程（Steps）
1. 创建并初始化 `QCodeMerged.html`。
2. 合并“生成器 / 解析器”两大模式。
3. 新增 PNG 导出尺寸能力（预设 + 自定义）。
4. 增加中英双语切换（UI 文案与主题名称联动）。
5. 落地 `task.md` 与 `walkthrough.md` 作为配套记录。

## 4. 变更清单（Changed Files）
- `QCodeMerged.html`（创建并持续修改）
- `task.md`（创建并更新）
- `walkthrough.md`（创建）

## 5. 验证与结果（Validation）
- 页面可在单文件场景直接打开运行。
- 生成与解析能力可在同一页面切换使用。
- PNG 尺寸导出逻辑可用。
- 中英文切换可覆盖关键交互文案。

## 6. 后续建议（Next）
- 为后续批处理功能预留统一数据结构，降低多模式之间的状态耦合。
