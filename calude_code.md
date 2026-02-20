# Claude CLI Complete Guide

This README provides a complete reference for using the Claude CLI
effectively, including commands, flags, examples, and real-world
workflows.

------------------------------------------------------------------------

# Table of Contents

-   Introduction
-   Installation Check
-   Basic Commands
-   Session Management
-   File Processing
-   Model Selection
-   Output Formats
-   Debugging
-   Directory Access
-   System Prompt Customization
-   Tool Permissions
-   Chrome Integration
-   Budget Control
-   Worktree Usage
-   Real-world Workflows
-   Best Practices

------------------------------------------------------------------------

# Introduction

Claude CLI allows you to interact with Claude directly from your
terminal. It helps with:

-   Code analysis
-   Debugging
-   Automation
-   Log analysis
-   Documentation generation
-   CI/CD workflows

------------------------------------------------------------------------

# Installation Check

Check version:

``` bash
claude -v
```

------------------------------------------------------------------------

# Basic Commands

## Interactive Mode

``` bash
claude
```

Use when: - Working continuously - Coding - Debugging

Outcome: Interactive terminal session.

------------------------------------------------------------------------

## Single Query Mode

``` bash
claude -p "Explain this code"
```

Use when: - Automation - Scripts

Outcome: Prints response and exits.

------------------------------------------------------------------------

# Session Management

Continue last session:

``` bash
claude -c
```

Resume specific session:

``` bash
claude -r session-name
```

------------------------------------------------------------------------

# File Processing

Analyze logs:

``` bash
cat logs.txt | claude -p "Find error"
```

Analyze code:

``` bash
cat main.py | claude -p "Explain this file"
```

------------------------------------------------------------------------

# Model Selection

``` bash
claude --model sonnet
claude --model opus
claude --model haiku
```



## Model Comparison

| Model  | Speed  | Quality  |
|--------|--------|----------|
| haiku  | Fast   | Low      |
| sonnet | Medium | High     |
| opus   | Slow   | Highest  |
------------------------------------------------------------------------

# Directory Access

Allow Claude to access project:

``` bash
claude --add-dir ./project
```

Use when: - Explaining projects - Debugging

------------------------------------------------------------------------

# Output Formats

Text:

``` bash
claude -p "Explain code"
```

JSON:

``` bash
claude -p "Explain code" --output-format json
```

------------------------------------------------------------------------

# Debug Mode

``` bash
claude --debug
```

Shows internal operations.

------------------------------------------------------------------------

# System Prompt Customization

Append prompt:

``` bash
claude --append-system-prompt "Always write optimized code"
```

Replace prompt:

``` bash
claude --system-prompt "You are Python expert"
```

------------------------------------------------------------------------

# Tool Permissions

Allow tools:

``` bash
claude --tools "Read,Edit,Bash"
```

Disallow tools:

``` bash
claude --disallowedTools "Edit"
```

------------------------------------------------------------------------

# Chrome Integration

``` bash
claude --chrome
```

Use for: - Web automation - Testing

------------------------------------------------------------------------

# Budget Control

``` bash
claude -p "Explain code" --max-budget-usd 5
```

Stops after budget reached.

------------------------------------------------------------------------

# Worktree Usage

``` bash
claude -w feature-branch
```

Creates isolated workspace.

------------------------------------------------------------------------

# Real-world Workflows

## Debug FastAPI

``` bash
claude --add-dir ./backend
```

Then:

    Find bugs in API

------------------------------------------------------------------------

## Analyze Logs

``` bash
cat logs.txt | claude -p "Find root cause"
```

------------------------------------------------------------------------

## Generate Documentation

``` bash
claude -p "Generate documentation" > docs.md
```

------------------------------------------------------------------------

# Best Practices

Recommended workflow:

``` bash
cd project
claude --add-dir .
```

Then:

    Explain project
    Find bugs
    Optimize code
    Generate tests

------------------------------------------------------------------------

# Summary

Claude CLI helps automate development workflows, debug faster, and
analyze code efficiently.
