# Autumn LaTeX Notes

![License](https://img.shields.io/badge/license-MIT-blue.svg)

一款典雅的学术风 LaTeX 笔记模板与 AI 生成技能，采用经典的 **牛津蓝 (Oxford Blue) & 勃艮第红 (Burgundy Red)** 配色方案。

## 🌟 核心特性

- **学术美学**：告别枯燥的纯文本排版。使用深邃的牛津蓝构建文档结构，搭配勃艮第红突出核心视觉焦点。
- **定制化排版框 (`tcolorbox`)**：
  - `conceptbox`（概念框）：用于承载定义、背景介绍和核心概念。
  - `theorembox`（定理框）：用于醒目展示定理、数学公式和关键结论。
  - `quotebox`（引用框）：极简的侧边线设计，适合原文摘抄与引用。
  - `warningbox`（警告框）：红色虚线框，用于记录易错点或重要警告。
- **原生中文支持**：基于 `ctexart` 文档类构建，完美适配中文排版规范。
- **开箱即用的 AI 技能 (AI Skill)**：本项目不仅包含模板，还提供了一套 AI 指令文件 (`SKILL.md`)。你可以直接让你的 AI 助手“按照这个格式生成笔记”，它将自动为你完成复杂的 LaTeX 代码排版！

## 🚀 如何作为模板使用 (独立使用)

1. 复制 `SKILL.md` 模板代码块中的 LaTeX 代码（或将其另存为 `.tex` 文件）。
2. 在 [Overleaf](https://www.overleaf.com/) 或你本地的 LaTeX 环境中打开。
3. **非常重要**：请务必将编译器设置为 **XeLaTeX**，以确保完美支持中文环境。

## 🤖 如何作为 AI 技能使用 (结合 AI Agent)

如果你使用的是支持 Agent 技能的 AI 助手（例如现在的环境），由于技能已安装完毕，以后你只需对 AI 发送指令：

> "@autumn-latex-notes 请帮我总结这篇网页/PDF的内容，并生成笔记。"

AI 就会自动识别文本类型，并将你的内容智能映射到本模板提供的各种精美 LaTeX 框体中，直接输出成品代码。

## 📄 开源协议

本项目基于 MIT 协议开源 - 详情请查看 LICENSE 文件。
