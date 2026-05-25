# QCode Toolkit — SVG QR Code Toolkit

> 一个纯前端、零构建、单文件部署的二维码瑞士军刀，支持 **生成 · 美化 · 解析** 三合一，可直接在浏览器中运行。  
> A frontend-only, zero-build, single-file QR code toolkit running in the browser — generate, beautify, and decode QR codes in one unified interface.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
![Platform](https://img.shields.io/badge/platform-browser-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)

🌐 **Live Demo**: [https://severinquan.github.io/qcode-toolkit/](https://severinquan.github.io/qcode-toolkit/)

---

## ✨ 功能亮点 / Features

| 功能 | 说明 |
|------|------|
| 🎨 **二维码生成** | 单条 / 批量输入，支持多主题与自定义样式 |
| 🖼️ **二维码美化** | 拖入普通二维码图片，自动解析并重新渲染为精美风格 |
| 🔍 **二维码解析** | 多文件拖拽识别，一键复制全部解析结果 |
| 📦 **批量导出** | 支持 PNG（自定义尺寸）与 SVG 矢量格式导出 |
| 🌐 **中英双语** | 界面全文案支持中文 / English 无缝切换 |
| 📄 **零构建部署** | 单个 HTML 文件即可运行，无需 npm、打包或构建步骤 |

---

## 🚀 快速上手 / Quick Start

无需构建步骤，直接在现代浏览器中打开即可：

```bash
# 克隆仓库
git clone https://github.com/SeverinQuan/qcode-toolkit.git

# 进入项目目录
cd qcode-toolkit

# macOS / Linux
open QCodeToolkit.html

# Windows
start QCodeToolkit.html
```

也可以直接打开 GitHub Pages 在线版本：

```text
https://severinquan.github.io/qcode-toolkit/
```

> **隐私提示 / Privacy Note**  
> 二维码内容的生成、解析与美化均在浏览器端完成，不会上传至本项目服务器。  
> QR code generation, decoding, and beautification are processed in the browser and are not uploaded to any project server.

---

## 📂 目录结构 / Project Structure

```text
QCode Toolkit/
├── index.html                 # GitHub Pages 入口文件
├── QCodeToolkit.html          # 主程序（单文件，直接运行）
├── README.md                  # 项目说明文档
├── LICENSE                    # MIT 开源协议
└── Doc/
    ├── QCodeMerged_*_施工记录_*.md   # 最新施工记录
    └── process_docs/                 # 开发过程文档（按阶段归档）
        ├── phase-01-合并与基础能力落地.md
        ├── phase-02-二维码美化批处理能力.md
        ├── phase-03-界面稳定性与交互一致性.md
        └── phase-04-SVG批量下载能力补充.md
```

---

## 🛠️ 使用说明 / Usage

### 生成模式 / Generator

1. 在顶部切换至 **二维码生成** 标签。
2. 单条模式：在输入框粘贴 URL 或文字内容，选择主题后生成二维码。
3. 批量模式：输入多条内容（每行一条或批量粘贴），一键批量生成。
4. 支持分别下载 PNG / SVG 格式文件。

### 美化模式 / Beautify

1. 切换至 **二维码美化** 标签。
2. 将一张或多张现有二维码图片拖入识别区。
3. 选择目标主题，系统会自动解析原二维码内容并重新渲染为精美样式。
4. 支持单项下载（SVG / PNG）或批量下载。

### 解析模式 / Extractor

1. 切换至 **二维码解析** 标签。
2. 拖入一张或多张二维码图片。
3. 系统自动识别二维码内容并列出结果。
4. 点击 **一键复制全部结果** 可批量复制解析内容。

---

## 🎨 内置主题 / Built-in Themes

QCode Toolkit 内置多组二维码视觉主题，包括：

- 👑 臻享 / 典藏：黑金、翡翠鎏金、皇家紫、星空夜色
- ✨ 基础 / 品牌：商务黑、支付宝蓝、微信绿、科技蓝
- 🏮 国风 / 雅致：素笺金朱、青花瓷、朱砂红、水墨灰黑
- 🌿 自然 / 治愈：抹茶、樱花、秋枫、冰川蓝
- 💎 极简 / 高级：深空灰、玫瑰金、摩卡咖啡

---

## 📋 开发历程 / Changelog

本项目经历了四个主要迭代阶段：

| 阶段 | 目标 | 关键成果 |
|------|------|----------|
| **Phase 01** | 合并与基础能力落地 | 形成统一入口，支持 PNG 导出与中英双语切换 |
| **Phase 02** | 二维码美化批处理能力 | 多文件拖拽批处理，支持单项与批量下载 SVG / PNG |
| **Phase 03** | 界面稳定性与交互一致性 | 三模式切换无抖动，统一最小高度基线 |
| **Phase 04** | SVG 批量下载能力补充 | 生成与美化两个批量入口均支持 SVG 一键导出 |

详细记录请参阅 [`Doc/process_docs/`](./Doc/process_docs/)。

---

## 🧩 技术说明 / Technical Notes

QCode Toolkit 是一个纯前端工具，核心逻辑运行在浏览器端。

当前版本主要包含：

- 单文件 HTML 页面结构
- CSS 视觉样式与响应式布局
- 浏览器端二维码生成、解析与下载逻辑
- SVG / PNG 双格式导出
- 中文 / English 双语界面切换

> 注：当前版本通过 CDN 加载部分前端库与字体资源，因此更准确的描述是 **零构建、单文件部署**，而不是严格意义上的“完全零依赖”。如需完全离线版本，可在后续版本中将相关资源本地化。

---

## 🤝 贡献指南 / Contributing

欢迎任何形式的贡献，包括功能建议、Bug 修复、文档优化与主题设计。

推荐流程：

1. **Fork** 本仓库并创建特性分支：

   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **提交** 你的变更：

   ```bash
   git commit -m "feat: add zip batch export"
   ```

3. **推送** 到你的 Fork：

   ```bash
   git push origin feature/your-feature-name
   ```

4. 提交 **Pull Request**，并在描述中说明改动内容、测试情况与相关截图。

### 提交信息规范 / Commit Convention

建议遵循 [Conventional Commits](https://www.conventionalcommits.org/)：

- `feat:` — 新功能
- `fix:` — Bug 修复
- `docs:` — 文档更新
- `style:` — 界面 / 样式调整（不影响逻辑）
- `refactor:` — 代码重构
- `chore:` — 工程维护或杂项调整

---

## 🐛 问题反馈 / Bug Reports

发现问题？请提交 Issue：

[https://github.com/SeverinQuan/qcode-toolkit/issues](https://github.com/SeverinQuan/qcode-toolkit/issues)

建议包含以下信息：

- 操作系统与浏览器版本
- 复现步骤
- 预期行为与实际行为
- 相关截图或录屏
- 控制台报错信息（如适用）

---

## 🔭 后续规划 / Roadmap

- [ ] ZIP 打包下载，减少大量文件触发浏览器多次保存提示
- [ ] 异常文件类型提示与失败项重试入口
- [ ] 移动端响应式分级最小高度策略
- [ ] 更多二维码主题与自定义颜色支持
- [ ] 完全离线版本：将字体与前端库资源本地化
- [ ] 多语言 README：English / 日本語 / 한국어 / Deutsch / Français / Português / Español

---

## 📄 许可证 / License

本项目基于 [MIT License](./LICENSE) 开源。

Copyright © 2026 QCode Toolkit Contributors
