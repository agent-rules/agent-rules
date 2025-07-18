# Agent Rules

## Summary

Agent Rules is a community standard for unifying guidelines for AI coding agents via standard configuration files, promoting interoperability across tools, initially a standard `AGENTS.md` file.

## Introduction

AI coding agents often rely on project-specific rules to guide their behavior. However, each tool uses its own configuration files, leading to redundancy and complexity. Agent Rules addresses this by proposing a unified configuration file. This allows developers to define rules once, while agents can incorporate them into their context alongside any proprietary formats. The specification is deliberately lightweight, focusing on natural language in Markdown, to encourage broad support and interoperability.

Initially the standard specifies a single `AGENTS.md` file; a simple specification for minimum interoperability.

This project is inspired by similar projects such as [Editor Config](https://editorconfig.org/), [Semantic Versioning](https://semver.org/), and [Conventional Commits](https://www.conventionalcommits.org/). Rather than have fragmented configuration systems, let's start early to have some common standards

Enhancements to the standards, such as folders, hierarchical files, and structured metadata (such as applicable file globs), to be discussed by the community. 

## Specification

The Agent Rules specification defines the minimal requirements for compatibility:

1. File Name and Location: A single file named AGENTS.md (case-sensitive) must be placed in the project root directory.
2. Content Format: The file must contain natural language instructions in Markdown or plain text, providing guidance for AI coding agents (e.g., rules, preferences, or workflows).
3. Usage by Agents: Agents must check for the existence of AGENTS.md in the project root. If present, its contents should be included in the agent's context scope (e.g., prepended or appended to prompts or system instructions). Agents may process it in conjunction with any custom or existing configuration files, falling back to defaults if absent.
4. No additional structure, metadata, or parsing is required beyond reading the file as text.

## Guidance for Use

While the specification allows flexible natural language, users of 'AGENTS.md' should follow these recommendations for clarity and effectiveness:

- The file should contain a flat, unordered bullet list of rules to keep it simple and scannable.
- Rules should be written as concise, imperative statements, using keywords like "must" or "should" for clarity (inspired by RFC 2119 conventions).
- Use Markdown headings sparingly if needed for organization, but avoid complex structures to maintain agent compatibility.
- Focus on project-specific guidance, such as coding standards, security checks, or testing requirements, to maximize utility across agents.

## Example

```markdown
- An agent may not injure a human being or, through inaction, allow a human being to come to harm.
- An agent must obey the orders given it by human beings except where such orders would conflict with the First Law.
- An agent must protect its own existence as long as such protection does not conflict with the First or Second Law.
```

Suitable additional examples, focussed on software development, are available in several agent projects.

## Support

- [Codex](https://github.com/openai/codex), scoped hierarchically.
