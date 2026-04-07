# Claude Code Subagents -- Complete Guide

This document explains how to:

-   Create a subagent
-   Use a subagent
-   Edit a subagent
-   Delete a subagent
-   Verify subagent status
-   Advanced and manual methods

------------------------------------------------------------------------

# What is a Subagent

A subagent is a specialized AI assistant with:

-   Its own system prompt
-   Its own tool permissions
-   Its own model selection
-   Its own context window
-   Optional persistent memory

Subagents allow you to isolate tasks such as:

-   Running tests
-   Reviewing code
-   Debugging errors
-   Generating APIs

------------------------------------------------------------------------

# Method 1: Create Agent Using `/agents` Command (Recommended)

## Step 1: Start Claude CLI

``` bash
claude
```

------------------------------------------------------------------------

## Step 2: Open Agents Interface

    /agents

This opens the agent management menu.

------------------------------------------------------------------------

## Step 3: Create New Agent

Select:

    Create new agent

------------------------------------------------------------------------

## Step 4: Select Scope

Choose one:

-   User-level → Available in all projects
-   Project-level → Available only in current project

Recommended:

    User-level

------------------------------------------------------------------------

## Step 5: Generate Agent with Claude

Example prompt:

    A test-runner agent that runs pytest tests, analyzes failures, and fixes issues automatically.

Claude generates configuration.

------------------------------------------------------------------------

## Step 6: Select Tools

Recommended tools:

-   Read
-   Edit
-   Write
-   Bash
-   Grep
-   Glob

------------------------------------------------------------------------

## Step 7: Select Model

Recommended:

    sonnet

------------------------------------------------------------------------

## Step 8: Save Agent

Agent is saved to:

Windows:

    C:\Users\<username>\.claude\agents\

Linux/Mac:

    ~/.claude/agents/

------------------------------------------------------------------------

# How to Use an Agent

Example usage:

    Use the test-runner agent to run all tests and fix failures

Explicit usage:

    Use the debugger subagent to fix this error

Claude automatically delegates task.

------------------------------------------------------------------------

# How to Edit an Agent

## Method 1: Using `/agents`

Run:

    /agents

Select:

    Edit agent

Choose agent name.

Modify:

-   Prompt
-   Tools
-   Model

Save.

------------------------------------------------------------------------

## Method 2: Manual Editing

Open file:

Windows:

    C:\Users\<username>\.claude\agents\agent-name.md

Example:

    test-runner.md

Edit content.

Restart Claude.

------------------------------------------------------------------------

# How to Delete an Agent

## Method 1: Using `/agents`

Run:

    /agents

Select:

    Delete agent

Select agent name.

Confirm.

------------------------------------------------------------------------

## Method 2: Manual Delete

Windows:

``` powershell
Remove-Item "$env:USERPROFILE\.claude\agents\test-runner.md"
```

Linux/Mac:

``` bash
rm ~/.claude/agents/test-runner.md
```

------------------------------------------------------------------------

# How to Verify Agent Exists

Run:

    /agents

OR manually:

Windows:

``` powershell
ls $env:USERPROFILE\.claude\agents
```

Linux/Mac:

``` bash
ls ~/.claude/agents
```

------------------------------------------------------------------------

# Manual Agent Creation

Step 1:

Create folder:

Windows:

    C:\Users\<username>\.claude\agents\

Step 2:

Create file:

    test-runner.md

Step 3:

Paste:

``` markdown
---
name: test-runner
description: Runs pytest tests and fixes failures
tools: Read, Edit, Write, Bash
model: sonnet
---

You are a pytest expert.

Tasks:

1. Run pytest
2. Identify failures
3. Fix issues
4. Verify fixes
```

Step 4:

Restart Claude.

------------------------------------------------------------------------

# CLI-Based Temporary Agent

``` bash
claude --agents '{
  "test-runner": {
    "description": "Runs pytest tests",
    "prompt": "You are a pytest expert",
    "tools": ["Read", "Edit", "Write", "Bash"],
    "model": "sonnet"
  }
}'
```

Valid only for current session.

------------------------------------------------------------------------

# Agent Storage Locations

User agents:

    ~/.claude/agents/

Project agents:

    project/.claude/agents/

Agent memory:

    ~/.claude/agent-memory/

------------------------------------------------------------------------

# Agent Lifecycle Summary

Create:

    /agents → Create → Save

Use:

    Use agent-name agent to perform task

Edit:

    /agents → Edit

Delete:

    /agents → Delete

Verify:

    /agents

------------------------------------------------------------------------

# Recommended Agents for Backend Projects

-   test-runner → Runs pytest
-   debugger → Fix errors
-   code-reviewer → Review code
-   api-generator → Generate FastAPI endpoints

------------------------------------------------------------------------

# Best Practices

-   Keep agents task-specific
-   Use minimal tool permissions
-   Use sonnet model for coding
-   Use user-level agents for reuse
-   Use project-level agents for team sharing

------------------------------------------------------------------------

# End of Guide
