# GEMINI.md

This file provides guidance to Gemini CLI when working with code in this repository.

## Project Overview

This is the Awesome Claude Agents repository, now optimized for Gemini CLI. It's a collection of specialized AI agents that extend capabilities through intelligent orchestration and domain expertise.

## 🚀 Core Capabilities

Our agentic ecosystem is designed for high-fidelity software engineering. Key enhanced agents include:

- **@tech-lead-orchestrator**: Strategic architect that designs executable roadmaps and coordinates sub-agents.
- **@code-reviewer**: Security-aware quality gate specializing in vulnerabilities, architectural alignment, and performance.
- **@database-wizard**: Expert in SQL/NoSQL schema design, zero-downtime migrations, and query optimization.
- **@docker-captain**: Master of containerization, multi-stage builds, and cloud-native infrastructure.

## Working with Agents

Gemini CLI uses **Subagents** for specialized tasks. These are defined in `.gemini/agents/`.
To use an agent, use the `@` syntax (e.g., `@tech-lead-orchestrator`) to delegate tasks.

### CRITICAL: Agent Routing Protocol

**When handling complex tasks, you MUST:**

1.  **START with @tech-lead-orchestrator** for any task involving more than 2 steps or architectural decisions.
2.  **STRICTLY FOLLOW** the execution roadmap and dependency graph provided by the Tech Lead.
3.  **DELEGATE** to the most specific specialist available (e.g., use `@django-orm-expert` instead of `@backend-developer` for Django database tasks).

## Orchestration Pattern

1.  **Discovery**: `@project-analyst` maps the tech stack and existing patterns.
2.  **Strategy**: `@tech-lead-orchestrator` breaks the requirement into a multi-phase plan.
3.  **Execution**: Specialized agents (e.g., `@react-component-architect`, `@python-expert`) implement specific modules.
4.  **Verification**: `@code-reviewer` validates the implementation against security and style standards.
5.  **Finalization**: `@documentation-specialist` updates relevant docs and changelogs.

## Available Subagents (by Category)

### 🏗️ Orchestration & Planning
`tech-lead-orchestrator`, `project-analyst`, `team-configurator`, `startup-cto`

### 🛡️ Core Quality & Infrastructure
`code-reviewer`, `code-archaeologist`, `performance-optimizer`, `documentation-specialist`, `incident-commander`, `tech-debt-surgeon`

### 🌐 Universal Specialists
`backend-developer`, `frontend-developer`, `api-architect`, `tailwind-css-expert`, `typescript-sage`, `workflow-automator`

### 🐍 Python & Data Science
`python-expert`, `django-expert`, `fastapi-expert`, `django-api-developer`, `django-orm-expert`, `ml-data-expert`, `web-scraping-expert`

### ⚛️ Frontend & UI/UX
`react-component-architect`, `react-nextjs-expert`, `nextjs-architect`, `react-wizard`, `storybook-artist`, `tailwind-artist`

### 💾 Databases & Storage
`database-wizard`, `postgresql-guru`, `supabase-specialist`

### 🚢 DevOps & Cloud
`docker-captain`, `nginx-wizard`, `devops-cicd-expert`

### 🧪 Testing & QA
`cypress-champion`, `testing-expert`

## Skills

Some agents are also available as **Skills** (e.g., `code-reviewer`). Use `activate_skill("code-reviewer")` for immediate procedural guidance within your current context.

## Development Guidelines

- **Source of Truth**: Agents are managed in the structured `agents/` directory and synced to `.gemini/agents/`.
- **Validation**: All non-trivial changes must be reviewed by `@code-reviewer`.
- **Idiomaticity**: Always prefer framework-specific agents to ensure idiomatic code (e.g., `@django-orm-expert` for Django database work).
