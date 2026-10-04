# Autumn LaTeX Notes

![License](https://img.shields.io/badge/license-MIT-blue.svg)

An elegant, academic LaTeX note-taking template and AI-generation skill, featuring an **Oxford Blue & Burgundy Red** color scheme.

## 🌟 Features

- **Academic Aesthetics**: Avoids standard plain text. Uses deep Oxford Blue for structures and Burgundy Red for emphasis.
- **Custom Environments (`tcolorbox`)**:
  - `conceptbox`: For definitions and core concepts.
  - `theorembox`: For theorems, mathematical formulas, and critical conclusions.
  - `quotebox`: Clean, side-lined boxes for excerpts and quotes.
  - `warningbox`: Dashed red boxes for common mistakes or warnings.
- **Native Chinese Support**: Powered by `ctexart`.
- **AI-Ready Skill Integration**: Includes an AI instruction file (`SKILL.md`) so you can simply ask your AI assistant to "convert text into my LaTeX notes" and it will do the formatting for you!

## 🚀 How to Use (Template)

1. Copy the LaTeX code from the `SKILL.md` (or save it as a `.tex` file).
2. Open it in [Overleaf](https://www.overleaf.com/) or your local LaTeX environment.
3. **Important**: Ensure your compiler is set to **XeLaTeX** to support the `ctexart` Chinese environment correctly.

## 🤖 Using as an AI Skill

If you are using an agentic AI system (like Antigravity), you can import the `SKILL.md` file into your agent's skill directory. Once loaded, simply prompt your agent:

> "@autumn-latex-notes Please summarize this webpage/PDF and generate the notes for me."

The AI will automatically map your text into the beautiful LaTeX environments provided by this template.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
