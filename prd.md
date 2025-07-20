Please use this guidance to generate a `prd-<topic>.md` file describing the users feature. Use the process outlined below
to generate the prd file.
<process>
# Product Requirements Document (PRD) Creation Guide
<overview>
This guide helps Claude generate detailed Product Requirements Documents (PRDs) in Markdown format based on user requests. PRDs must be clear, actionable, and suitable for junior developers to understand and implement.
</overview>

<process-flow>
<initial-input>
- User provides brief description or request for new feature/functionality
- Do NOT start implementing immediately
</initial-input>

<clarification-phase>
- ALWAYS ask clarifying questions before writing PRD
- Focus on understanding "what" and "why", not "how" 
- Provide options in letter/number lists for easy user responses
- Goal: gather sufficient detail to create comprehensive requirements
</clarification-phase>

<generation-phase>
- Create PRD using structured format outlined below
- Base content on initial prompt + user's clarifying answers
- Write for junior developer audience - be explicit and unambiguous
</generation-phase>

<output-phase>
- Save as `prd-[feature-name].md` in `/tasks` directory
- Use Markdown format exclusively
</output-phase>
</process-flow>

<clarifying-questions>
<question-categories>
Adapt questions based on user prompt, but explore these key areas:

<problem-definition>
- "What problem does this feature solve for the user?"
- "What is the main goal we want to achieve with this feature?"
- "Why is this feature important right now?"
</problem-definition>

<user-context>
- "Who is the primary user of this feature?"
- "What is their current workflow/process?"
- "How tech-savvy are they?"
</user-context>

<functionality-scope>
- "Can you describe the key actions a user should be able to perform?"
- "What's the minimum viable version of this feature?"
- "Are there any specific things this feature should NOT do?"
</functionality-scope>

<user-stories>
- "Could you provide user stories in format: As a [user type], I want to [action] so that [benefit]"
- "What would a typical user journey look like?"
</user-stories>

<success-criteria>
- "How will we know when this feature is successfully implemented?"
- "What are the key success metrics?"
- "What does 'done' look like?"
</success-criteria>

<data-requirements>
- "What kind of data does this feature need to display/manipulate?"
- "Where does this data come from?"
- "How should data be structured?"
</data-requirements>

<design-constraints>
- "Are there existing design mockups or UI guidelines?"
- "Can you describe the desired look and feel?"
- "Should this match existing components/patterns?"
</design-constraints>

<edge-cases>
- "What error conditions should we handle?"
- "What happens when things go wrong?"
- "Are there any potential edge cases?"
</edge-cases>
</question-categories>
</clarifying-questions>

<prd-structure>
Generate PRD with these sections in order:

<section-1-introduction>
- Brief feature description
- Problem it solves
- High-level goal statement
</section-1-introduction>

<section-2-goals>
- Specific, measurable objectives
- Use bullet points
- Focus on outcomes, not features
</section-2-goals>

<section-3-user-stories>
- Detailed user narratives
- Format: "As a [user type], I want to [action] so that [benefit]"
- Include primary and secondary user flows
</section-3-user-stories>

<section-4-functional-requirements>
- Numbered list of specific functionalities
- Use clear, actionable language
- Example: "The system must allow users to upload a profile picture"
- Be explicit and unambiguous for junior developers
</section-4-functional-requirements>

<section-5-non-goals>
- What feature will NOT include
- Scope boundaries
- Future considerations moved out of scope
</section-5-non-goals>

<section-6-design-considerations>
- UI/UX requirements
- Link to mockups if available
- Relevant components/styles to follow
- Accessibility requirements
</section-6-design-considerations>

<section-7-technical-considerations>
- Known technical constraints
- Dependencies on existing systems
- Integration requirements
- Performance considerations
</section-7-technical-considerations>

<section-8-success-metrics>
- Measurable success criteria
- Examples: "Increase user engagement by 10%", "Reduce support tickets by 25%"
- Both quantitative and qualitative measures
</section-8-success-metrics>

<section-9-open-questions>
- Remaining areas needing clarification
- Dependencies on other teams/decisions
- Items to research further
</section-9-open-questions>
</prd-structure>

<target-audience>
<primary-reader>
- Junior developer with basic understanding of the codebase
- May not know business context or domain expertise
- Needs explicit, step-by-step requirements
- Avoid jargon and assumptions
</primary-reader>

<writing-guidelines>
- Use simple, direct language
- Provide enough context for implementation decisions
- Include examples where helpful
- Be specific about expected behavior
- Avoid ambiguous terms like "intuitive" or "user-friendly"
</writing-guidelines>
</target-audience>

<critical-reminders>
<before-starting>
- Do NOT start implementing the PRD immediately
- MUST ask clarifying questions first
- Provide multiple choice options for easy responses
</before-starting>

<output-requirements>
- Format: Markdown (.md)
- Location: /tasks/ directory
- Filename: prd-[feature-name].md
- Replace [feature-name] with descriptive kebab-case name
</output-requirements>
</critical-reminders>
</process>

<feature-description>
$ARGUMENTS
</feature-description>