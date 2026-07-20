# obsidian-note-organizer-skill
A Claude Code skill for organizing Obsidian study notes.
# Obsidian Note Organizer Skill

A lightweight Claude Code skill for reorganizing raw Obsidian notes into structured study notes.

It organizes notes into:

- Main titles and subheadings
- Key concepts
- Questions and answers
- Examples
- Obsidian image embeds
- Formulas, code blocks and internal links

## Installation

### Method 1: Copy the skill folder

Download this repository and copy:

```text
.claude/skills/organize-note/
```

into the `.claude/skills/` directory of your Obsidian vault.

The final structure should be:

```text
YourVault/
└─ .claude/
   └─ skills/
      └─ organize-note/
         └─ SKILL.md
```

Restart Claude Code or Claudian after installation.

### Method 2: Clone the repository

Clone this repository:

```bash
git clone https://github.com/YOUR-USERNAME/obsidian-note-organizer-skill.git
```

Then copy the skill folder into your Obsidian vault:

```text
obsidian-note-organizer-skill/.claude/skills/organize-note/
```

## Usage

In Claude Code or Claudian, run:

```text
/organize-note @your-note.md
```

To save the reorganized note to another file:

```text
/organize-note @source-note.md output to "Notes/organized-note.md"
```

## Notes

- The skill reads only the explicitly selected note.
- It does not scan the entire vault.
- It preserves Obsidian image embeds, links, formulas and code blocks.
- It does not inspect image pixels.
- It edits the source note unless another output path is provided.

## License

MIT
