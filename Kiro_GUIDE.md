# Kiro - AI Assistant & IDE Guide

## What is Kiro?

Kiro is an AI-powered assistant and IDE built to help developers write, debug, and maintain code efficiently. I work alongside you as a knowledgeable partner, understanding your codebase and providing intelligent assistance.

## Current Model

**Claude Sonnet 4.5** - A powerful AI model designed for complex coding tasks, deep reasoning, and natural conversation.

## Core Features

### 1. Intelligent Code Assistance
- Write, edit, and refactor code across multiple languages
- Understand your entire codebase context
- Provide syntax-aware suggestions and fixes
- Automatic import and reference updates when renaming or moving files

### 2. Autonomy Modes
- **Autopilot Mode**: I can modify files autonomously within your workspace
- **Supervised Mode**: You review and approve changes before they're applied

### 3. Context-Aware Chat
- Use `#File` or `#Folder` to reference specific files/folders
- Attach images and documents (PDF, DOCX) by dragging them into chat
- Access `#Problems`, `#Terminal`, and `#Git Diff` for real-time context
- I can see diagnostics and errors in your current files

### 4. Web Access & Research
- Search the internet for current documentation and solutions
- Fetch content from specific URLs
- Stay updated with latest library versions and best practices
- Verify information across multiple sources

### 5. Specs (Structured Development)
- Formalize feature design and implementation
- Break complex features into manageable tasks
- Iterate on requirements, design, and implementation
- Reference external files like OpenAPI or GraphQL specs using `#[[file:filename]]`

### 6. Agent Hooks (Automation)
Automate actions based on IDE events:

**Event Types:**
- `fileEdited`, `fileCreated`, `fileDeleted` - File system events
- `promptSubmit`, `agentStop` - Chat events
- `preToolUse`, `postToolUse` - Before/after tool execution
- `preTaskExecution`, `postTaskExecution` - Spec task events
- `userTriggered` - Manual trigger

**Actions:**
- `askAgent` - Send me a reminder or instruction
- `runCommand` - Execute shell commands automatically

**Example**: Auto-lint TypeScript files on save
```json
{
  "name": "Lint on Save",
  "version": "1.0.0",
  "when": {
    "type": "fileEdited",
    "patterns": ["*.ts", "*.tsx"]
  },
  "then": {
    "type": "runCommand",
    "command": "npm run lint"
  }
}
```

### 7. Steering Files (Custom Instructions)
Add project-specific context and standards in `.kiro/steering/*.md`:

- **Always included** (default) - Applied to all interactions
- **Conditional** - Triggered when specific files are opened
- **Manual** - Activated via `#` context key in chat

Reference external files: `#[[file:openapi.yaml]]`

### 8. Model Context Protocol (MCP)
Extend capabilities with MCP servers:

- Configure in `.kiro/settings/mcp.json` (workspace) or `~/.kiro/settings/mcp.json` (global)
- Auto-approve trusted tools
- Enable/disable servers as needed
- Servers reconnect automatically on config changes

**Example MCP Configuration:**
```json
{
  "mcpServers": {
    "aws-docs": {
      "command": "uvx",
      "args": ["awslabs.aws-documentation-mcp-server@latest"],
      "env": {
        "FASTMCP_LOG_LEVEL": "ERROR"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

### 9. Sub-Agents (Specialized Assistance)
Delegate tasks to specialized agents:

- **context-gatherer** - Explore unfamiliar codebases and identify relevant files
- **general-task-execution** - Handle well-defined subtasks independently
- **custom-agent-creator** - Create new specialized agents for recurring tasks

### 10. Advanced Code Operations
- **Semantic Rename**: Rename symbols (functions, classes, variables) across the entire codebase
- **Smart Relocate**: Move/rename files with automatic import updates
- **Diagnostics**: Real-time syntax, linting, and type checking
- **Code Reading**: AST-based analysis for large files with symbol search

## How to Use Kiro

### Basic Workflow
1. **Ask questions** - I'll provide clear, actionable answers
2. **Request changes** - I'll modify your code with minimal, focused edits
3. **Review & iterate** - Provide feedback and I'll refine the solution

### Best Practices
- Reference specific files with `#File` for precise context
- Use Autopilot mode for faster iterations
- Create hooks for repetitive tasks
- Add steering files for project standards
- Let me search the web when you need current information

### Example Interactions
- "Fix the authentication bug in `#backend/auth.py`"
- "Add error handling to all API endpoints"
- "Explain how the payment flow works" (I'll explore the codebase)
- "What's the latest version of React?"
- "Create a hook to run tests after each commit"

## Platform Support

Currently running on:
- **OS**: Windows
- **Platform**: win32
- **Shell**: bash

Commands are automatically adapted to your platform.

## Getting Help

- Use the command palette and search for "Kiro" or "MCP" for relevant commands
- Open the Agent Hooks view in the explorer to manage automation
- Check `.kiro/steering/` for custom instructions
- Ask me anything - I'm here to help!

## What I Can Do

✅ Write and modify code
✅ Debug and fix errors
✅ Explain complex concepts
✅ Search the web for current info
✅ Automate repetitive tasks
✅ Refactor and optimize code
✅ Manage project structure
✅ Test and validate changes

