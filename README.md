<div align="center">

# Obsidian Note Organizer Skill

[![English](https://img.shields.io/badge/Language-English-blue)](./README.md)
[![简体中文](https://img.shields.io/badge/语言-简体中文-red)](./README.zh-CN.md)

A lightweight Claude Code skill for turning raw Obsidian notes into structured study notes.

</div>

## Features

This skill organizes notes into:

- Main titles and topic-based headings
- Clear explanations of key concepts
- Questions and answers
- Helpful examples
- Obsidian image embeds
- Formulas, code blocks, callouts, tags, and internal links

It reads only the note explicitly selected by the user and does not scan the entire Obsidian vault.

## Installation

### Option 1: Download ZIP

1. Click **Code → Download ZIP** on this repository.
2. Extract the downloaded archive.
3. Copy the following folder:

```text
.claude/skills/organize-note/
```

4. Paste it into the `.claude/skills/` directory of your Obsidian vault.

The final structure should be:

```text
YourVault/
└─ .claude/
   └─ skills/
      └─ organize-note/
         └─ SKILL.md
```

Restart Obsidian, Claudian, or Claude Code after installation.

### Option 2: Clone with Git

Clone this repository:

```bash
git clone https://github.com/YOUR-USERNAME/obsidian-note-organizer-skill.git
```

Then copy:

```text
obsidian-note-organizer-skill/.claude/skills/organize-note/
```

to:

```text
YourVault/.claude/skills/
```

Replace `YOUR-USERNAME` with the GitHub username of the repository owner.

## Usage

Open Claude Code or Claudian and run:

```text
/organize-note @your-note.md
```

By default, the skill edits the selected note directly.

To create a separate organized note:

```text
/organize-note @source-note.md output to "Notes/organized-note.md"
```

## Behavior

The skill:

- Reads only the explicitly selected Markdown note
- Does not scan the complete vault
- Does not open linked notes
- Preserves YAML frontmatter and tags
- Preserves Obsidian internal links
- Preserves formulas and code blocks
- Preserves image embeds such as `![[image.png]]`
- Moves images near the most relevant topic
- Extracts questions and provides answers when possible
- Adds examples only when they improve understanding
- Avoids repeating the rewritten note in the chat

The skill does not inspect image pixels. Add a short image description near an image when its visual content is important.

## Example

Input:

```markdown
PID controls output using P I D.

Why does increasing P sometimes cause oscillation?

![[pid-response.png]]
```

Possible organized result:

```markdown
# PID Control

## Proportional Control

### Key Concept

The proportional term produces an output based on the current error.

> [!question] Why can increasing proportional gain cause oscillation?
> A larger proportional gain makes the controller respond more aggressively.
> If the gain is too large, the system may repeatedly overshoot the target.

**Example:**

Increasing proportional gain can shorten rise time while increasing overshoot.

![[pid-response.png]]
```

## Updating

Download the newest version of the repository and replace:

```text
YourVault/.claude/skills/organize-note/
```

Your personal notes and Claudian conversations are not stored inside this skill folder.

## License

This project is licensed under the [MIT License](./LICENSE).
