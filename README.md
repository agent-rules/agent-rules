# Agent Rules

## Summary

Agent Rules is a community standard for unifying guidelines for AI coding agents via standard
configuration files, promoting interoperability across tools, initially a standard `AGENTS.md` file.

## Introduction

AI coding agents often rely on project-specific rules to guide their behavior. However, each tool
uses its own configuration files, leading to redundancy and complexity. Agent Rules addresses this
by proposing a unified configuration file. This allows developers to define rules once, while agents
can incorporate them into their context alongside any proprietary formats. The specification is
deliberately lightweight, focusing on natural language in Markdown, to encourage broad support and
interoperability.

Initially the standard specifies a single `AGENTS.md` file; a simple specification for minimum
interoperability.

This project is inspired by similar projects such as [Editor Config](https://editorconfig.org/),
[Semantic Versioning](https://semver.org/), and
[Conventional Commits](https://www.conventionalcommits.org/). Rather than have fragmented
configuration systems, let's start early to have some common standards

Enhancements to the standards, such as folders, hierarchical files, and structured metadata (such as
applicable file globs), to be discussed by the community.

## Specification

The Agent Rules specification defines the minimal requirements for compatibility, with key words
“MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”,
and “OPTIONAL” interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt):

1. File Name and Location: Agents implementing Agent Rules MUST check for the existence of
   `AGENTS.md` in the project root. If present, its contents SHOULD be included in the agent's
   context scope (e.g., prepended or appended to prompts or system instructions).
2. Content Format: The file MUST be parsed as natural language instructions, in Markdown or plain
   text, and MUST be used to provide guidance to AI coding agents (e.g., rules, preferences, or
   workflows).
3. Agents MUST NOT require additional structure, metadata, or parsing beyond reading the file as
   text.
4. Agents MAY process it in conjunction with any custom or existing configuration files, falling
   back to defaults if absent.
5. Agents MAY also check for and include any `AGENTS.md` file in the current working directory,
   incorporating its contents into the context scope alongside the project root `AGENTS.md` if
   present.

## Guidance for use

While the specification allows flexible natural language, users of `AGENTS.md` should follow these
recommendations for clarity and effectiveness:

- The file should contain a flat, unordered bullet list of rules to keep it simple and scannable.
- Rules should be written as concise, imperative statements, using keywords like "MUST" or "SHOULD"
  for clarity (inspired by RFC 2119 conventions).
- Use Markdown headings sparingly if needed for organization, but avoid complex structures to
  maintain agent compatibility.
- Focus on project-specific guidance, such as coding standards, security checks, or testing
  requirements, to maximize utility across agents.

## Example

```markdown
- An agent MUST NOT (write code to) injure a human being or, through inaction, allow a human being
  to come to harm.
- An agent MUST obey the orders given it by human beings except where such orders would conflict
  with the First Law.
- An agent MUST protect its own existence as long as such protection does not conflict with the
  First or Second Law.
```

Suitable additional examples, focussed on software development, are available in several agent
projects.

## Tools that support Agent Rules

- [Codex](https://github.com/openai/codex), scoped hierarchically.
