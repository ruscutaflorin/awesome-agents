# GEMINI.md

This file provides guidance to Gemini CLI when working with code in this repository.

## Project Overview

This is the Awesome Claude Agents repository, now optimized for Gemini CLI. It's a collection of specialized AI agents that extend capabilities through intelligent orchestration and domain expertise.

## Working with Agents

Gemini CLI uses **Subagents** for specialized tasks. These are defined in `.gemini/agents/`.
To use an agent, use the `@` syntax or delegate tasks to them based on their expertise.

### CRITICAL: Agent Routing Protocol

**When handling complex tasks, you SHOULD:**

1. **START with @tech-lead-orchestrator** for any multi-step task or major feature.
2. **FOLLOW the agent routing map** returned by the tech-lead.
3. **DELEGATE to specific subagents** using the `@name` syntax (e.g., `@django-backend-expert`).

## Orchestration Pattern

1. **Research & Analysis**: Use `@project-analyst` to understand the tech stack.
2. **Strategy & Planning**: Use `@tech-lead-orchestrator` to break down tasks.
3. **Execution**: Delegate to specialized agents (e.g., `@react-component-architect`, `@python-expert`).
4. **Validation**: Use `@code-reviewer` or the `code-reviewer` skill for final quality checks.

## Available Subagents

- **Orchestrators**: `tech-lead-orchestrator`, `project-analyst`, `team-configurator`
- **Core Specialists**: `code-reviewer`, `code-archaeologist`, `performance-optimizer`, `documentation-specialist`
- **Universal Specialists**: `backend-developer`, `frontend-developer`, `api-architect`, `tailwind-css-expert`
- **Python Specialists**: `python-expert`, `django-expert`, `fastapi-expert`, `django-api-developer`, `django-orm-expert`, `ml-data-expert`, `security-expert`, `web-scraping-expert`, `testing-expert`, `performance-expert`, `devops-cicd-expert`
- **Frontend Specialists**: `react-component-architect`, `react-nextjs-expert`, `vue-component-architect`, `vue-state-manager`, `vue-nuxt-expert`
- **PHP Specialists**: `laravel-backend-expert`, `laravel-eloquent-expert`
- **Ruby Specialists**: `rails-backend-expert`, `rails-api-developer`, `rails-activerecord-expert`

## Skills

Some agents are also available as **Skills** (e.g., `code-reviewer`). Use `activate_skill("code-reviewer")` when you need procedural expertise without leaving the current context history.

## Development Guidelines

- Agents are located in `.gemini/agents/*.md`.
- Skills are located in `.gemini/skills/`.
- Always prefer framework-specific agents over universal ones.
- Ensure all changes are validated by a code review.
