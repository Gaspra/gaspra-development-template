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
- **Work Chunking & Task Assignment**:
  - When given a definition of work, analyze and split the work into logically parallel working chunks.
  - Assign each chunk to a specific agent role and codename.
- **Agent Initialization**:
  - If a new agent or role needs to be created, create its development tracker space:
    1. Create the directory `.agents/development/<codename>/`.
    2. Register the agent in the roster inside `.agents/development/development-agents.md`, adding the codename, role, active conversation ID, and durable notes.
    3. Create `.agents/development/<codename>/agent.md` outlining the persona, role, and context setup for the agent.
- **Instruction Delivery & Handoff**:
  - Create `.agents/development/<codename>/instructions.md` inside each assigned agent's directory containing:
    - **Header**: Active metadata including `Status: Pending`.
    - **Task Description**: Comprehensive definition of the work chunk, requirements, and boundaries.
    - **Task Checklist**: A clear Markdown checklist of steps.
    - **Handoff Note**: Clear instructions specifying that the agent must mark items as `[x]` as they complete tasks, update the header to `Status: Completed` when done, append a chronological log entry to their `journal.md`, and notify the user/Project Manager when finished.