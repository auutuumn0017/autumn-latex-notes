---
name: autumn-latex-notes
description: Autumn 专属的“牛津蓝+勃艮第红”经典学术 LaTeX 笔记生成器。自动将非结构化学习资料重构为精美的排版代码。
---

# Autumn LaTeX Notes Generator

当用户请求你生成 LaTeX 笔记，或者调用 `@autumn-latex-notes` 处理资料时，你必须严格遵循以下规则。

## 工作目标
将用户提供的非结构化内容（文本、总结、网页摘录等）提炼并转化为结构化的、可直接编译的 LaTeX 代码。

## 内容映射规则 (Content Mapping Rules)
在处理用户内容时，你需要智能地识别内容类型，并将其放入对应的 LaTeX 环境中：

1. **大纲与结构**：提取逻辑并使用 `\section{}` 和 `\subsection{}` 组织。
2. **概念、定义、背景信息**：必须放入 `\begin{conceptbox}[标题] ... \end{conceptbox}` 中。
3. **定理、核心公式、至关重要的结论**：必须放入 `\begin{theorembox}[标题] ... \end{theorembox}` 中。
4. **原文摘抄、名人名言、引用**：放入 `\begin{quotebox} ... \end{quotebox}` 中。
5. **易错点、警告、注意事项**：放入 `\begin{warningbox} ... \end{warningbox}` 中。
6. **行内公式与强调**：
   - 数学公式使用 `$ ... $` 或 `\begin{equation}`。
   - 需要高亮的重点词汇使用 `\hl{重点词汇}`。
   - 需要红色加粗的极重要词汇使用 `\imp{极重要词汇}`。

## 强制 LaTeX 模板
你生成的回复**必须**包含完整的 LaTeX 代码（包含导言区），并且**只能使用以下预设的导言区和定义**。你只需要修改 `\title{}` 以及 `\begin{document} ... \end{document}` 之间的内容。

```latex
\documentclass[UTF8, 11pt, a4paper]{ctexart}
\usepackage[left=2.5cm, right=2.5cm, top=3cm, bottom=3cm]{geometry}
\usepackage{xcolor, fancyhdr, titlesec, hyperref, amsmath, amssymb, amsthm}
\usepackage[many]{tcolorbox}
\usepackage{enumitem}

% ==========================================
% 颜色定义 (Autumn Notes Theme)
% ==========================================
\definecolor{OxfordBlue}{RGB}{0, 33, 71}
\definecolor{Burgundy}{RGB}{128, 0, 32}
\definecolor{LightGrey}{RGB}{248, 249, 250}
\definecolor{Highlight}{RGB}{255, 243, 205}

\newcommand{\hl}[1]{\colorbox{Highlight}{#1}}
\newcommand{\imp}[1]{\textbf{\color{Burgundy}#1}}

\hypersetup{colorlinks=true, linkcolor=OxfordBlue, urlcolor=OxfordBlue}

\pagestyle{fancy}
\fancyhf{}
\fancyhead[L]{\color{OxfordBlue}\textbf{《阅读笔记》}}
\fancyhead[R]{\color{OxfordBlue}\leftmark}
\fancyfoot[C]{\thepage}
\renewcommand{\headrulewidth}{0.8pt}
\renewcommand{\headrule}{\hbox to\headwidth{\color{OxfordBlue}\leaders\hrule height \headrulewidth\hfill}}

\titleformat{\section}{\Large\bfseries\color{OxfordBlue}}{\thesection}{1em}{}[\titlerule]
\titleformat{\subsection}{\large\bfseries\color{OxfordBlue!85!black}}{\thesubsection}{1em}{}

% 1. 定义/概念框
\newtcolorbox{conceptbox}[1][]{
    enhanced, colback=LightGrey, colframe=OxfordBlue, fonttitle=\bfseries,
    title=#1, attach boxed title to top left={yshift=-2mm, xshift=5mm},
    boxed title style={colback=OxfordBlue, sharp corners=all, rounded corners=northeast},
    arc=2mm, drop fuzzy shadow
}

% 2. 定理/公式框
\newtcolorbox{theorembox}[1][]{
    enhanced, colback=Burgundy!5, colframe=Burgundy, fonttitle=\bfseries,
    title=#1, attach boxed title to top left={yshift=-2mm, xshift=5mm},
    boxed title style={colback=Burgundy, sharp corners=all, rounded corners=northeast},
    arc=2mm, drop fuzzy shadow
}

% 3. 原文摘抄框
\newtcolorbox{quotebox}{
    colback=OxfordBlue!3, colframe=OxfordBlue,
    leftrule=4pt, rightrule=0pt, toprule=0pt, bottomrule=0pt, arc=0pt
}

% 4. 警告框
\newtcolorbox{warningbox}{
    enhanced, colback=white, colframe=Burgundy,
    boxrule=1pt, arc=1mm, borderline={0.5pt}{2pt}{Burgundy, dashed},
    title=\textcolor{Burgundy}{\textbf{⚠️ 注意/易错点}}, coltitle=Burgundy,
    attach title to upper, after title={\par\smallskip}
}

\title{\vspace{-2cm}\color{OxfordBlue}\Huge\textbf{阅读与学习笔记}}
\author{Autumn}
\date{\today}

\begin{document}
\maketitle
\tableofcontents
\thispagestyle{empty}
\newpage

% [在这里根据用户提供的内容组织排版]

\end{document}
```
