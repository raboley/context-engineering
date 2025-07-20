# Contributing Guidelines

<context-requirements>
- Always read `prd-[feature].md` first to understand project architecture, goals, and constraints
- Check `tasks-.md` before starting new tasks - add unlisted tasks with brief description and date
- Use consistent naming conventions, file structure, and architecture patterns per `PLANNING.md`
- Use the project's designated environment/runtime when executing commands, including tests
</context-requirements>

<code-structure>
<file-limits>
- Maximum 500 lines per file - refactor by splitting into modules if approaching limit
</file-limits>

<organization>
- Organize code into clearly separated modules grouped by feature or responsibility
- Use clear, consistent imports following language best practices
- Use appropriate environment variable management for the language/framework
- Use appropriate logging framework for observability with full execution context
</organization>
</code-structure>

<testing-requirements>
<test-philosophy>
- Only create end-to-end tests using actual data and real connections
- Black box test how users would actually test the system
- Isolate test context to enable parallel execution
- Prefer integration tests over mocked tests when feasible
</test-philosophy>

<test-configuration>
- Follow project's parallel testing configuration for faster execution
- Ensure proper credentials and configuration via environment variables
- Expect responses in format used by project's data handling framework
</test-configuration>

<test-maintenance>
- After updating logic, check if existing unit tests need updates
- Run tests to ensure everything still works
- Include minimum test coverage:
  - 1 test for expected use
  - 1 edge case test
  - 1 failure case test
  - 1 test ensuring new components are properly registered/integrated
</test-maintenance>

<test-quality-standards>
<function-structure>
- NO docstrings on test functions - function names should be self-explanatory
- NO comments explaining test steps - code should be clear without explanation
- NO print statements or celebratory output - assertions are sufficient
</function-structure>

<assertion-requirements>
- Use descriptive assertion messages with context - explain both what should happen AND what actually happened
- For comparisons, always show expected vs actual values using f-strings
- For boolean checks, explain the opposite condition (e.g., "should fetch from API, but was retrieved from cache")
- Make failure messages informative - include all context needed to understand and fix failures
- ALWAYS test the end result - verify what the user would see, not just that something didn't crash
- Test actual behavior - don't assume success, verify the expected outcome occurred
</assertion-requirements>

<assertion-examples>
BAD: `assert x == y, "Should be equal"`
GOOD: `assert x == y, f"Expected {y} but got {x}"`

BAD: `assert success, "Should succeed"`
GOOD: `assert success, f"Expected operation to succeed but failed: {error_details}"`
</assertion-examples>

<test-workflow>
- NO "fire and forget" testing - always validate the actual outcome
</test-workflow>
</test-quality-standards>
</testing-requirements>

<task-completion>
<validation>
- Always run tests ensuring all pass before marking tasks complete
- Use project's designated test command
</validation>

<tracking>
- Mark completed tasks in `TASK.md` immediately after finishing
- Add discovered sub-tasks/TODOs to `TASK.md` under "Discovered During Work" section
- Request feedback before moving to next feature task
</tracking>

<task-list-maintenance>
<update-protocol>
- Update task list as you work through implementation
- Mark tasks and subtasks as completed ([x]) following completion protocol
- Add new tasks as they emerge during development
- Regularly update after finishing any significant work
</update-protocol>

<completion-protocol>
- Mark each finished sub-task with [x]
- Mark parent task [x] only once ALL its subtasks are [x]
- Before starting work, check which sub-task is next
- After implementing a sub-task, update the file and pause for user approval
</completion-protocol>

<relevant-files-maintenance>
- Maintain "Relevant Files" section accuracy throughout development
- List every file created or modified during implementation
- Give each file a one-line description of its purpose
- Keep descriptions current as file purposes evolve
</relevant-files-maintenance>

<ai-task-instructions>
When working with task lists, the AI must:
- Regularly update the task list file after finishing any significant work
- Follow the completion protocol exactly as specified above
- Add newly discovered tasks as they emerge
- Keep "Relevant Files" section accurate and up to date
- Before starting work, check which sub-task is next
- After implementing a sub-task, update the file and pause for user approval
</ai-task-instructions>
</task-list-maintenance>
</task-completion>

<style-conventions>
<language-framework>
- Follow project's primary language and framework conventions
- Use project's designated package manager per documentation
- Use project's build system for all build and test commands
- Follow language-specific style guidelines with appropriate type systems
- Format code with project's chosen formatter
</language-framework>

<data-handling>
- Use appropriate data validation libraries for chosen language/framework
- Strongly type data structures - create datatypes for all received/sent structures
- Use appropriate frameworks for APIs and data persistence per project specs
</data-handling>

<documentation>
- Write comprehensive documentation for every public function/method
- Use language's standard documentation format
- Update `README.md` when features are added, dependencies change, or setup steps modify
- Only comment code to explain WHY, never WHAT (unless non-obvious)
</documentation>
</style-conventions>

<ai-behavior-rules>
<assumptions>
- Never assume missing context - ask questions if uncertain
- Never hallucinate libraries or functions - only use known, verified packages
- Always confirm file paths and module names exist before referencing
- Never delete or overwrite existing code unless explicitly instructed or per `TASK.md`
</assumptions>

<planning>
- Always plan features vertically including:
  - Code implementation
  - End-to-end tests
  - Observability integration
  - Code documentation
</planning>
</ai-behavior-rules>