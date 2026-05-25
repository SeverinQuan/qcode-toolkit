# QCode Toolkit — SVG QR Code Toolkit

> 一个纯前端、零依赖部署的二维码瑞士军刀，支持**生成 · 美化 · 解析**三合一，单文件直接在浏览器中运行。  
> A zero-dependency, single-file QR code toolkit running entirely in the browser — generate, beautify, and decode in one unified interface.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
![Platform](https://img.shields.io/badge/platform-browser-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)

---

## ✨ 功能亮点 / Features

| 功能 | 说明 |
|------|------|
| 🎨 **二维码生成** | 单条 / 批量输入，支持多主题与自定义样式 |
| 🖼️ **二维码美化** | 拖入普通二维码图片，自动重新渲染为精美风格 |
| 🔍 **二维码解析** | 多文件拖拽识别，一键复制全部结果 |
| 📦 **批量导出** | PNG（自定义尺寸）& SVG 矢量格式双格式导出 |
| 🌐 **中英双语** | 界面全文案中英无缝切换 |
| 📄 **零依赖部署** | 单个 HTML 文件，离线可用，无需构建步骤 |

---

## 🚀 快速上手 / Quick Start

无需安装任何依赖，直接在现代浏览器中打开即可：

```bash
# 克隆仓库
git clone https://github.com/SeverinQuan/qcode-toolkit.git

# 直接用浏览器打开主文件
open QCodeToolkit.html
# 或在 Windows 上：
start QCodeToolkit.html
```

> **提示**：本工具完全在浏览器端运行，所有数据均不上传至任何服务器，保证隐私安全。

---

## 📂 目录结构 / Project Structure

```
QCode Toolkit/
├── QCodeToolkit.html          # 主程序（单文件，直接运行）
├── LICENSE                    # MIT 开源协议
└── Doc/
    ├── QCodeMerged_*_施工记录_*.md   # 最新施工记录
    └── process_docs/          # 开发过程文档（按阶段归档）
        ├── README.md          # 文档索引
        ├── phase-01-合并与基础能力落地.md
        ├── phase-02-二维码美化批处理能力.md
        ├── phase-03-界面稳定性与交互一致性.md
        ├── phase-04-SVG批量下载能力补充.md
        ├── process-01.md ~ process-04.md  # 详细施工日志
        └── ...
```

---

## 🛠️ 使用说明 / Usage

### 生成模式

1. 在顶部切换至 **生成** 标签。
2. 单条模式：在输入框粘贴 URL 或文字内容，选择主题，点击生成。
3. 批量模式：输入多条内容（每行一条），一键批量生成，支持分别下载 PNG / SVG。

### 美化模式

1. 切换至 **美化** 标签。
2. 将一张或多张现有二维码图片拖入识别区。
3. 选择目标主题，系统自动解析并重新渲染为精美风格。
4. 支持单项下载（SVG / PNG）或批量打包下载。

### 解析模式

1. 切换至 **解析** 标签。
2. 拖入一张或多张二维码图片。
3. 自动识别内容并列出结果，点击"一键复制全部结果"。

---

## 📋 开发历程 / Changelog

本项目经历了四个主要迭代阶段：

| 阶段 | 目标 | 关键成果 |
|------|------|----------|
| **Phase 01** | 合并与基础能力落地 | 统一 `QCodeMerged.html` 入口，PNG 导出，中英双语切换 |
| **Phase 02** | 二维码美化批处理能力 | 多文件拖拽批处理，单项 & 批量下载 SVG / PNG |
| **Phase 03** | 界面稳定性与交互一致性 | 三模式切换无抖动，统一最小高度基线 |
| **Phase 04** | SVG 批量下载能力补充 | 生成 & 美化两个批量入口均支持 SVG 一键导出 |

详细记录请参阅 [`Doc/process_docs/`](./Doc/process_docs/)。

---

## 🤝 贡献指南 / Contributing

欢迎任何形式的贡献！请遵循以下流程：

1. **Fork** 本仓库并创建您的特性分支：
   ```bash
   git checkout -b feature/your-feature-name
   ```
2. **提交** 您的变更（请使用语义化提交信息）：
   ```bash
   git commit -m "feat: 添加 ZIP 批量打包下载功能"
   ```
3. **推送** 到您的 Fork：
   
   ```bash
   git push origin feature/your-feature-name
   ```
4. 提交 **Pull Request**，并在描述中说明改动内容和测试情况。

### 提交信息规范

遵循 [Conventional Commits](https://www.conventionalcommits.org/)：

- `feat:` — 新功能
- `fix:` — Bug 修复
- `docs:` — 文档更新
- `style:` — 界面/样式调整（不影响逻辑）
- `refactor:` — 代码重构
- `chore:` — 构建/工具链相关

---

## 🐛 问题反馈 / Bug Reports

发现问题？请 [提交 Issue](https://github.com/your-org/qcode-toolkit/issues)，并尽量包含：

- 操作系统与浏览器版本
- 复现步骤
- 预期行为与实际行为
- 相关截图（如适用）

---

## 📄 许可证 / License

本项目基于 [MIT License](./LICENSE) 开源。  
Copyright © 2026 QCode Toolkit Contributors

---

## 🔭 后续规划 / Roadmap

- [ ] ZIP 打包下载，减少大量文件触发浏览器多次保存提示
- [ ] 异常文件类型提示与失败项重试入口
- [ ] 移动端响应式分级最小高度策略
- [ ] 更多二维码主题与自定义颜色支持
