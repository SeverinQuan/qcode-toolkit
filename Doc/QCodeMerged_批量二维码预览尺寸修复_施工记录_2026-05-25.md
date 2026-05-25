# QCodeMerged_批量二维码预览尺寸修复_施工记录_2026-05-25

## 结论

- 本次完成了 `QCodeMerged.html` 批量二维码预览尺寸修复：批量生成区与批量美化区的预览实例从 `300x300` 改为原生 `64x64`，移除了批量预览依赖 `setTimeout` 追加 SVG 属性的脆弱逻辑。
- 下载路径已改为下载前临时放大到 `300x300`，下载结束后通过 `finally` 恢复 `64x64`，避免预览框显示 300px SVG 的局部切片。
- 当前已完成静态源码核对与浏览器交互验证。

## 改动范围

- `sample/QCodeMerged.html`：修复生成模式批量预览实例尺寸、批量下载后恢复尺寸。
- `sample/QCodeMerged.html`：修复美化模式批量预览实例尺寸、单项下载与批量下载后恢复尺寸。
- `sample/QCodeMerged.html`：保留上一轮已加入的 `shrink-0 overflow-hidden` 容器约束与预览前清空容器逻辑。

## 关键实现

- 生成模式 `renderGenerateBatchList()` 中，批量预览 `QRCodeStyling` 初始化尺寸改为 `width: 64, height: 64`，`imageOptions.margin` 从 `10` 缩小为 `2`。
- 美化模式 `reRenderBeautifyBatchItems()` 中，批量预览 `QRCodeStyling` 初始化尺寸同样改为 `64x64`。
- 删除批量预览渲染后用于强行设置 `svg width/height/viewBox` 的 `setTimeout` 逻辑，避免 `.update()` 重绘后属性丢失。
- 生成批量下载、美化单项下载、美化批量下载均使用 `try/finally`：下载前 `update({ width: 300, height: 300 })`，下载后 `update({ width: 64, height: 64 })`。

## 验证情况

- 已运行 `rg -n "width: 64, height: 64|width: 300, height: 300|setTimeout\\(\\(\\) =>|downloadBeautifyBatchItem|finally|previewContainer\\.innerHTML = ''|previewDiv\\.innerHTML = ''" "D:\\Lite Studio\\sample\\QCodeMerged.html"`，确认批量预览实例为 `64x64`，下载路径存在恢复尺寸逻辑，批量区域的 SVG 属性补丁已移除。
- 已运行 `git -C "D:\\Lite Studio" status --short --ignored -- "sample/QCodeMerged.html"`，确认 `sample/` 目录被 Git 忽略，因此该样例文件不会出现在普通 `git diff` 中。
- 已用 Codex in-app browser 打开 `file:///D:/Lite%20Studio/sample/QCodeMerged.html`，在生成区输入两条批量数据后确认生成 2 个预览 SVG，首个 SVG 的 `width`/`height` 均为 `64`。
- 已在浏览器中编辑第一条批量数据，确认 `.update()` 后首个预览 SVG 的 `width`/`height` 仍为 `64`。
- 已在浏览器中点击生成区批量下载按钮，等待下载路径执行后确认首个预览 SVG 的 `width`/`height` 仍恢复为 `64`，浏览器控制台错误数为 0。

## 风险与回滚

- 风险：`qr-code-styling` 的 `download()` 若内部异步读取发生在调用返回之后，过快恢复尺寸可能影响导出尺寸；当前保留了下载前等待重绘的 `100ms/200ms` 延迟，并在调用后恢复预览。
- 回滚方式：将批量预览实例尺寸恢复为 `300x300`，并恢复原先的 `setTimeout` SVG 属性补丁；不建议回滚到该方案，因为它仍会受 `.update()` 重绘影响。

## 后续建议

- 用浏览器打开 `sample/QCodeMerged.html`，在批量生成模式输入多条数据并连续编辑其中一项，确认预览不再出现局部放大。
- 对批量美化模式拖入多张二维码图片，检查滚动性能与下载后的预览尺寸是否保持稳定。
