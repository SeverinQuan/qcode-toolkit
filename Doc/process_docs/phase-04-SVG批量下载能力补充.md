# Phase 04：SVG 批量下载能力补充

## 1. 目标（Goal）
在“二维码生成（批量）”和“二维码美化（批量）”两个流程中补全 SVG 一键批量下载能力，形成 PNG + SVG 双格式批量导出。

## 2. 对应 Skill（Skill Mapping）
- `frontend-skill`：新增按钮与现有主次操作样式协同。
- `code-change-log`：批量导出能力变更说明。

## 3. 实施过程（Steps）
1. 在批量下载区域新增 `.SVG` 按钮，并与 `.PNG` 并排展示。
2. 扩展中英双语词典，补充 SVG 批量下载文案。
3. 复用既有批处理任务遍历机制，接入 SVG 导出分支。
4. 确保“生成批量模式”和“美化批量模式”均可触发。

## 4. 变更清单（Changed Files）
- `QCodeMerged.html`
- `task.md`
- `walkthrough.md`

## 5. 验证与结果（Validation）
- 两个批量入口均可一键下载 SVG。
- 下载文件与任务列表项一一对应。
- UI 样式与原有按钮体系保持一致。

## 6. 后续建议（Next）
- 可追加“ZIP 打包下载”减少大量文件触发浏览器多次保存提示。
