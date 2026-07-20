<div align="center">

# Obsidian 笔记整理 Skill

[![English](https://img.shields.io/badge/Language-English-blue)](./README.md)
[![简体中文](https://img.shields.io/badge/语言-简体中文-red)](./README.zh-CN.md)

一个用于将 Obsidian 原始笔记整理为结构化学习笔记的轻量级 Claude Code Skill。

</div>

## 功能

该 Skill 可以将笔记整理为：

- 清晰的大标题和主题小标题
- 经过梳理的核心知识点
- 疑问与解答
- 帮助理解的简短示例
- Obsidian 图片嵌入
- 公式、代码块、Callout、标签和内部链接

它只读取用户明确指定的笔记，不会扫描整个 Obsidian 仓库。

## 安装方法

### 方法一：下载 ZIP

1. 在本仓库页面点击 **Code → Download ZIP**。
2. 解压下载的压缩包。
3. 复制以下文件夹：

```text
.claude/skills/organize-note/
```

4. 将其粘贴到 Obsidian 仓库的 `.claude/skills/` 文件夹中。

最终目录结构应为：

```text
你的Obsidian仓库/
└─ .claude/
   └─ skills/
      └─ organize-note/
         └─ SKILL.md
```

安装完成后，重新启动 Obsidian、Claudian 或 Claude Code。

### 方法二：使用 Git 克隆

克隆本仓库：

```bash
git clone https://github.com/YOUR-USERNAME/obsidian-note-organizer-skill.git
```

然后复制：

```text
obsidian-note-organizer-skill/.claude/skills/organize-note/
```

到：

```text
你的Obsidian仓库/.claude/skills/
```

请将 `YOUR-USERNAME` 替换为仓库所有者的 GitHub 用户名。

## 使用方法

在 Claude Code 或 Claudian 中输入：

```text
/organize-note @你的笔记.md
```

默认情况下，Skill 会直接修改所选笔记。

需要另存为一篇新笔记时，可以输入：

```text
/organize-note @原始笔记.md output to "整理笔记/新笔记.md"
```

## 工作方式

该 Skill 会：

- 只读取明确指定的 Markdown 笔记
- 不扫描整个 Obsidian 仓库
- 不主动打开双链指向的其他笔记
- 保留 YAML frontmatter 和标签
- 保留 Obsidian 内部链接
- 保留公式和代码块
- 保留 `![[图片.png]]` 形式的图片嵌入
- 将图片移动到相关知识点附近
- 提取原笔记中的疑问并尽可能给出解答
- 只在有助于理解时添加示例
- 不在聊天窗口中重复输出整理后的完整笔记

该 Skill 不会读取图片的像素内容。图片内容很重要时，建议在图片附近添加简短的文字说明。

## 使用示例

原始笔记：

```markdown
PID由P I D组成。

为什么P增大后有时会振荡？

![[pid响应.png]]
```

可能得到：

```markdown
# PID控制

## 比例控制

### 核心知识点

比例环节根据当前误差的大小产生控制输出。

> [!question] 为什么增大比例增益可能导致振荡？
> 增大比例增益会使控制器响应更加激烈。
> 当增益过大时，系统可能反复越过目标值，从而产生振荡。

**示例：**

增大比例增益通常可以缩短上升时间，但也可能增大超调量。

![[pid响应.png]]
```

## 更新方法

下载仓库的最新版本，然后替换：

```text
你的Obsidian仓库/.claude/skills/organize-note/
```

你的个人笔记和 Claudian 对话不会保存在该 Skill 文件夹中。

## 开源许可证

本项目采用 [MIT License](./LICENSE)。
