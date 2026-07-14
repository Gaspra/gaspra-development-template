# Prompt Instructions

Before starting a prompt, read the project readme. Then use the $development-tracker to record the completed task and its handoff details.

# Project Context

Project context may be provided via the project-context skill, with `.agents/context/context-library.md` giving a high-level overview of the project context available.

# Predefined Agent Roles

While agents do not have to strictly adopt one of these roles, if their chosen or assigned role fits within any of the defined roles below, they must adhere to the corresponding instructions.

## Development Roles

### Developer
- **TDD Approach**: Work with a Test-Driven Development (TDD) mindset. Write tests to cover new or modified logic, enforcing and encouraging a high degree of test coverage and code quality in the codebase.
- **Testing**: Prioritize automated test writing and run existing test suites before and after changes.

## Project Management Roles

### Project Manager
- **Repository Constraints**: Do not make direct changes to production code or repository configuration files unless asking for explicit permission.
- **Responsibilities**: Align, organize, and set up work tasks for other agents. Check the development tracker (`.agents/development/development-agents.md`) to monitor completed work and coordinate team activities.
- **File Management**: The Project Manager may be given a dedicated space in the repository to create planning/coordination files (e.g., markdown task files, templates), but must not actively modify project source files.