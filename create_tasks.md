# Task List Generation from PRD Guide

<overview>
This guide helps Claude generate detailed, step-by-step task lists in Markdown format based on existing Product Requirements Documents (PRDs). Task lists must guide developers through complete vertical implementation where each feature includes code, tests, observability, and documentation.
</overview>

<vertical-planning-principle>
<core-philosophy>
**Always Plan Features Vertically** - Each feature component must include:
- Implementation code
- End-to-end tests  
- Observability/logging
- Code documentation

**Critical**: Do NOT bundle all testing and documentation at the end. Each task should be shippable with its complete vertical slice.
</core-philosophy>
</vertical-planning-principle>

<process-flow>
<phase-1-input>
- User provides reference to specific PRD file
- Read and analyze the PRD thoroughly
- Focus on functional requirements, user stories, and technical considerations
</phase-1-input>

<phase-2-parent-tasks>
- Generate main, high-level tasks (typically ~5 tasks)
- Each parent task should represent a complete vertical slice
- Present tasks without sub-tasks initially
- Include implementation + tests + observability + docs in each parent task scope
- Inform user: "I have generated the high-level tasks based on the PRD. Ready to generate the sub-tasks? Respond with 'Go' to proceed."
</phase-2-parent-tasks>

<phase-3-confirmation>
- MUST wait for user to respond with "Go"
- Do not proceed to sub-tasks without explicit confirmation
</phase-3-confirmation>

<phase-4-detailed-breakdown>
- Break down each parent task into actionable sub-tasks
- Ensure each parent task includes its complete vertical implementation
- Sub-tasks must logically follow from parent and cover all PRD requirements
- Include relevant file identification and testing strategy
</phase-4-detailed-breakdown>

<phase-5-output>
- Save as `tasks-[prd-file-name].md` in `/tasks/` directory
- Use specified Markdown structure exactly
</phase-5-output>
</process-flow>

<task-structure-requirements>
<vertical-slice-breakdown>
Each parent task should be a complete vertical slice containing:
- Core implementation sub-tasks
- Testing sub-tasks (integrated, not bundled at end)
- Observability/logging sub-tasks  
- Documentation sub-tasks
- Each parent task should be independently shippable
</vertical-slice-breakdown>

<sub-task-guidelines>
- Break down parent tasks into specific, actionable items
- Include file creation/modification steps
- Specify testing requirements per component
- Include logging/observability integration
- Add documentation requirements
- Ensure logical sequence within each parent task
</sub-task-guidelines>
</task-structure-requirements>

<file-identification>
<relevant-files-section>
Must identify potential files needing creation/modification:
- Implementation files with brief descriptions
- Corresponding test files for each implementation file
- Utility/helper files if needed
- Configuration files if applicable
- Documentation files

Format: `path/to/file.ext` - Brief description of purpose
</relevant-files-section>

<testing-file-conventions>
- Unit tests alongside code files they test
- Use project's testing framework conventions
- Include test file paths in relevant files section
- Reference appropriate test running commands
</testing-file-conventions>
</file-identification>

<output-format>
<required-structure>
The generated task list MUST follow this exact structure:

```markdown
## Relevant Files

- `path/to/potential/file1.ts` - Brief description of why this file is relevant
- `path/to/file1.test.ts` - Unit tests for `file1.ts`
- `path/to/another/file.tsx` - Brief description of purpose
- `path/to/another/file.test.tsx` - Unit tests for `another/file.tsx`
- `lib/utils/helpers.ts` - Utility functions description
- `lib/utils/helpers.test.ts` - Unit tests for `helpers.ts`

### Notes

- Use appropriate test runner commands per project configuration
- Each parent task represents a complete vertical slice (code + tests + observability + docs)

## Tasks

- [ ] 1.0 Parent Task Title (Complete Vertical Slice)
  - [ ] 1.1 [Implementation sub-task]
  - [ ] 1.2 [Testing sub-task for 1.1]
  - [ ] 1.3 [Observability sub-task for 1.1]
  - [ ] 1.4 [Documentation sub-task for 1.1]
  - [ ] 1.5 [Additional implementation if needed]
- [ ] 2.0 Parent Task Title (Complete Vertical Slice)
  - [ ] 2.1 [Implementation sub-task]
  - [ ] 2.2 [Testing sub-task for 2.1]
  - [ ] 2.3 [Observability integration]
- [ ] 3.0 Parent Task Title (may not require sub-tasks if simple)
```
</required-structure>

<filename-convention>
- Format: `tasks-[prd-file-name].md`
- Location: `/tasks/` directory
- Example: PRD `prd-user-profile-editing.md` → Task list `tasks-prd-user-profile-editing.md`
</filename-convention>
</output-format>

<interaction-model>
<two-phase-approach>
1. **Phase 1**: Generate and present parent tasks only
2. **Pause**: Wait for user confirmation with "Go" 
3. **Phase 2**: Generate detailed sub-tasks after confirmation

This ensures high-level plan alignment before detailed breakdown.
</two-phase-approach>

<confirmation-requirements>
- Must explicitly wait for "Go" response
- Do not proceed to sub-task generation without confirmation
- Present parent tasks clearly before pausing
</confirmation-requirements>
</interaction-model>

<target-audience>
<primary-reader>
- Junior developer implementing the feature
- Needs clear, step-by-step guidance
- Should understand each task's purpose and context
- Must be able to ship incremental value with each parent task
</primary-reader>

<writing-guidelines>
- Use actionable language for sub-tasks
- Be specific about file operations needed
- Include context for why each step is necessary
- Ensure tasks build logically on each other
- Make each parent task independently valuable
</writing-guidelines>
</target-audience>

<critical-reminders>
<vertical-planning>
- Never bundle testing/documentation at the end
- Each parent task must be a complete, shippable vertical slice
- Include implementation, testing, observability, and docs in each slice
- Tasks should be independently valuable and deployable
</vertical-planning>

<process-adherence>
- Must read and analyze PRD before generating tasks
- Must wait for "Go" confirmation between phases
- Must use exact output format specified
- Must save in correct location with correct filename
</process-adherence>
</critical-reminders>