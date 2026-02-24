# agent-teams-skills

A Claude Code skill for generating [Agent Teams](https://code.claude.com/docs/en/agent-teams) planning prompts. It analyzes your problem description and role requirements, then produces a complete, structured prompt system for orchestrating multi-agent collaboration.

## Features

- Parses core problems and role configurations from user input
- Proactively asks clarifying questions when roles are ambiguous or incomplete
- Generates self-contained prompts for each agent (Orchestrator + specialized agents)
- Defines clear input/output contracts and collaboration workflows between agents
- Outputs a review-ready plan before implementation

## Installation

Copy the skill file to your Claude Code commands directory:

```bash
# Global (available in all projects)
cp skills/create-teams.md ~/.claude/commands/

# Or project-level (current project only)
mkdir -p .claude/commands
cp skills/create-teams.md .claude/commands/
```

## Usage

In Claude Code, run:

```
/create-teams <your problem description and role requirements>
```

### Example

```
/create-teams
## Core Problems
1. Cross-platform UX fragmentation: users cannot seamlessly continue work on mobile
2. Interactive command rendering: mobile terminal cannot dynamically render CLI output
3. Mobile UI quality: current design is too basic

## Agent Roles
1. Research & Analysis Agent
2. UX Audit Agent
3. QA Agent
```

The skill will generate a complete agent teams plan including:
- Role overview table
- Orchestrator agent prompt (with TeamCreate/TaskCreate/SendMessage tool guidance)
- Each specialized agent's prompt (with responsibilities, boundaries, I/O specs)
- ASCII collaboration flow diagram
- Implementation instructions

All output is displayed in terminal for your review before implementation.

## License

[Apache-2.0](LICENSE)
