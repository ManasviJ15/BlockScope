---
description: How to execute a personal task assignment from the task list
---

# Personal Task Execution Workflow

This workflow defines the standard process for executing personal tasks assigned by the user. Follow these steps in order.

## 1. Analyze the Task
// turbo-all
- Read the task description carefully
- Identify all deliverables and acceptance criteria
- Check if there are dependencies on other tasks
- Note the estimated time and priority level

## 2. Explore the Codebase
- Explore the project structure to understand existing code
- Identify files that need to be created, modified, or deleted
- Look for existing implementations that cover parts of the task
- Check for hardcoded values, duplicated code, or stale files

## 3. Create Implementation Plan
- Create `implementation_plan.md` artifact with:
  - Background context and what the change accomplishes
  - Items requiring user review (breaking changes, design decisions)
  - Proposed changes grouped by component
  - Verification plan (automated + manual)
- Request user approval via `notify_user` before starting execution
- If user requests changes, update the plan and re-request review

## 4. Execute Changes
- Create/update `task.md` artifact as a task checklist
- Mark items `[/]` when starting and `[x]` when completed
- Make changes following the approved plan
- Use proper git-friendly practices:
  - No hardcoded secrets (use environment variables)
  - Follow existing code style and conventions
  - Add appropriate documentation and comments

## 5. Verify Changes
- Run existing tests to verify no regressions
- Perform manual verification checks from the plan
- Scan for any remaining issues (hardcoded secrets, missing files, etc.)
- Verify all deliverables from the task are complete

## 6. Create Report
- Create `walkthrough.md` artifact documenting:
  - All changes made (files created, modified, deleted)
  - What was tested and validation results
  - Any issues found and how they were resolved
- Present the report to the user via `notify_user`

## 7. Push to Repository
- **WAIT for explicit user confirmation** before pushing
- Only push after user says to push
- Push to the appropriate branch (main unless specified otherwise)
- Use descriptive commit messages

## Important Rules
- **Always ask questions** before starting if anything is unclear
- **Never push without explicit confirmation** from the user
- **Remove all hardcoded secrets** — use environment variables
- **Follow existing patterns** — match the codebase style
- **Update task.md** throughout execution to track progress
- **Create high-quality, production-ready** code — not MVPs
