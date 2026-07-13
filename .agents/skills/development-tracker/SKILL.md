---
name: development-tracker
description: Record durable, project-local history for completed AI-agent tasks. Use when work needs a handoff record, decisions and validation must be preserved, an agent codename or role must be registered, or a user asks to track completed development work or project history.
---

# Development Tracker

Record completed work in `.agents/development`. Keep the skill reusable; never store project history inside the skill directory.

## Start of task

1. Read `.agents/development/development-agents.md`. Open only task records relevant to the current work.
2. Capture the task start timestamp in local ISO 8601 format with a timezone when available.
3. Resolve the agent codename:
   - Use a user-supplied codename when one is provided.
   - Reuse the existing codename for the same recurring role or workstream when one is suitable.
   - Otherwise create a unique, human-readable codename of three lowercase words joined by hyphens. Check the agent roster and `.agents/development` directories before choosing it.
4. Use the user-supplied role when available. Otherwise choose the concise role that best describes the task.

## Complete a task

1. Create one completion record at `.agents/development/<codename>/YYYYMMDD-HHmm-<task-slug>.md`, using the task start time in the filename. Use a lowercase hyphenated task slug. If the path exists, append `-2`, then increment the suffix until the path is unique.
2. Write the record in this format:

   ```markdown
   # <Task title>

   - Agent codename: <codename>
   - Agent role: <role>
   - Prompt timestamp: <ISO 8601 timestamp>
   - Completion timestamp: <ISO 8601 timestamp>
   - Time to complete: <duration>

   ## Summary

   <Concise handover for future agents.>

   ## Decisions

   - <Decision and rationale, or `None beyond completing the requested task.`>

   ## Validation

   - <Checks performed and their outcome, or `Not applicable.`>

   ## Follow-ups

   - <Required follow-up, or `None.`>
   ```

3. Update `.agents/development/development-agents.md`:
   - Add the codename, role, and concise durable notes to the agent roster when it is new. Update notes only when durable role or handoff context changes.
   - Prepend one newest-first entry to Recent completed work, linking to the new record and summarising its purpose in one line.
4. Verify that the record path exists, the agent roster matches the record metadata, and the Recent completed work link resolves to the record.

## Boundaries

- Create records only when a task is complete. Do not create in-progress logs or separate progress entries.
- Keep records compact. Preserve decisions, validation, and follow-ups; do not reproduce full prompts, command logs, or file-by-file diffs.
- Do not overwrite an existing record or modify unrelated agent history.
