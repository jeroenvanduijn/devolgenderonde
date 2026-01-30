# Agent Instructions

> This file mirrors the shared AGENTS.md from `.shared-skills/`

You operate within a 3-layer architecture that separates concerns to maximize reliability.

## The 3-Layer Architecture

**Layer 1: Directive (What to do)**
- SOPs written in Markdown, live in `directives/`
- Define goals, inputs, tools/scripts, outputs, and edge cases

**Layer 2: Orchestration (Decision making)**
- This is the AI. Job: intelligent routing.
- Read directives, call execution tools, handle errors, update directives

**Layer 3: Execution (Doing the work)**
- Deterministic Python scripts in `execution/`
- Handle API calls, data processing, file operations

## Directory Structure

```
directives/     # SOPs in Markdown
execution/      # Python scripts
.tmp/           # Intermediate files (gitignored)
.env            # Environment variables (gitignored)
```

## Operating Principles

1. **Check for tools first** - Before writing a script, check `execution/`
2. **Self-anneal when things break** - Fix, update directive, test again
3. **Update directives as you learn** - Directives are living documents
