---
name: organize-note
description: Reorganize one Obsidian note into a clear, structured study note.
disable-model-invocation: true
argument-hint: "@source-note [output-path]"
allowed-tools:
  - Read
  - Edit
  - Write
---

Reorganize the single Obsidian Markdown note explicitly provided by the user.

If an output path is provided, write the result there. Otherwise, edit the source note directly.

## Scope

- Read only the specified note.
- Do not scan the vault.
- Do not open linked notes.
- Do not use web search.
- Do not inspect image pixels.
- Do not create a plan.
- Do not ask for confirmation.
- Complete the task in one pass.

## Structure

Organize the note with meaningful headings:

# Main Title

## Topic

### Key Concepts

Explain the topic clearly.

### Questions and Answers

> [!question] Question
> Question text.

> [!success] Answer
> Answer text.

### Example

**Example:**

A short example that helps explain the concept.

Do not force every topic to contain every subsection. Add sections only when useful.

## Editing Rules

1. Preserve useful source information.
2. Merge duplicated content.
3. Fix obvious grammar, spelling, and Markdown hierarchy errors.
4. Preserve YAML frontmatter, tags, internal links, formulas, code blocks, and callouts.
5. Preserve personal questions and class notes.
6. Do not invent facts, formulas, data, conclusions, or image content.
7. Add concise explanations only when they can be derived reliably.
8. Use lists, tables, formulas, and code blocks when they improve clarity.
9. Do not add conversational introductions or closing summaries.

## Images

Preserve every Obsidian image embed exactly, for example:

![[image-name.png]]

Move each image near the most relevant topic.

Do not rename or remove image links.

Do not describe an image unless the source note already provides enough information.

Format existing image descriptions as:

> Image note: description

## Questions

Convert questions, unclear statements, and unexplained conclusions into:

> [!question] Question
> Question text.

> [!success] Answer
> Answer text.

If the source note does not contain enough information:

> [!warning] Needs clarification
> The source note does not provide enough information.

## Examples

Add a short example only for abstract, confusing, procedural, or calculation-based concepts.

Do not add unnecessary examples to simple facts.

## Final Response

Do not paste the rewritten note into the chat.

Reply only with:

Done: <file-path>

Commit message:
Add organize-note skill
