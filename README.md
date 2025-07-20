# Context Engineering for Claude Code

A structured workflow for building production-ready software with Claude Code using PRDs, task planning, and vertical feature development.

## Quick Setup

Copy the workflow files to Claude's commands directory:

**Linux/macOS:**
```bash
cp create_prd.md create_tasks.md complete_tasks.md ~/.claude/commands/
```

**Windows:**
```cmd
copy create_prd.md %USERPROFILE%\.claude\commands\
copy create_tasks.md %USERPROFILE%\.claude\commands\
copy complete_tasks.md %USERPROFILE%\.claude\commands\
```

## Workflow

### 1. Create a Product Requirements Document
```
/create_prd "Build an MCP server for Azure DevOps that can run pipelines and get failure logs"
```

### 2. Break down into tasks
```
/create_tasks
```

### 3. Execute the tasks
```
/complete_tasks
```

## What This Gives You

- **Structured Planning**: PRDs with proper requirements gathering
- **Vertical Development**: Each task includes code + tests + docs + observability  
- **End-to-End Testing**: Real integration tests, not mocked fantasies
- **Production Ready**: Working software, not prototype spaghetti

## Key Files

- `CREATE_PRD.md` - Guides Claude through proper requirements gathering
- `CREATE_TASKS.md` - Breaks features into shippable vertical slices  
- `complete_tasks.md` - Execution workflow with testing and documentation
- `CONTRIBUTING.md` - Development standards and conventions

Start with `/create_prd` and let the workflow guide you to production-ready software.