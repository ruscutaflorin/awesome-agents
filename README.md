# Awesome Gemini Agents

This repository provides a powerful collection of specialized AI agents and skills designed for the **Gemini CLI** (originally adapted from a Claude Code implementation). By leveraging Gemini's native custom **Subagents** and **Skills** architecture, this repository transforms your CLI into a fully coordinated, multi-agent virtual development team.

## Core Concepts

In the Gemini CLI, functionality is extended in two primary ways:

1. **Subagents (`.gemini/agents/*.md`):** Specialized experts that run in their own isolated context loops. They are perfect for deep, focused tasks (like building a React component or tuning a database) without cluttering your main conversation history.
2. **Skills (`.gemini/skills/*/SKILL.md`):** Reusable procedural workflows that inject expertise directly into your *current* session. They are ideal for repeatable processes like code reviews.
3. **Orchestrators:** Meta-agents that analyze your codebase and requirements to route tasks to the correct subagents.

---

## Getting Started

This repository is pre-configured to work out-of-the-box with the Gemini CLI.

1. Ensure you have the Gemini CLI installed.
2. Navigate to this repository's root directory in your terminal.
3. Start the CLI:
   ```bash
   gemini
   ```
*(Note: The `.gemini/settings.json` file in this repository automatically enables the required `enableAgents` experimental feature).*

---

## How to Use

### 1. Direct Agent Invocation (Targeted Tasks)
If you know exactly what you need, you can summon a specific expert by using the `@` symbol followed by their name.

**Example:**
> `@django-backend-expert Please write a Django model for a User Profile with a OneToOne field to the default User model.`

**Example:**
> `@react-component-architect Create a responsive Tailwind navigation bar in Next.js.`

### 2. Orchestrated Workflow (Complex Multi-Step Tasks)
For large features, architecture decisions, or when you are unsure where to start, use the Tech Lead Orchestrator. The main agent will consult the Tech Lead, which will break down the project and route tasks to the correct specialists.

**Example:**
> `Please consult @tech-lead-orchestrator to design and build a full-stack login feature.`

### 3. Using Skills (Procedural Workflows)
Skills activate automatically when your prompt matches their description, or you can invoke them directly. They guide the main agent through a strict procedure.

**Example:**
> `Review the recent changes to the authentication module.` *(This will automatically trigger the `code-reviewer` skill)*

You can also manage skills by typing `/skills` in the CLI.

---

## Available Agents Directory

All subagents are defined as Markdown files in the `.gemini/agents/` directory. Here is a breakdown of the available virtual team members:

### 🧠 Orchestrators
*   `@tech-lead-orchestrator`: Analyzes complex projects, breaks them into tasks, and routes them to specialists.
*   `@project-analyst`: Analyzes new/unfamiliar codebases to detect frameworks and architecture.
*   `@team-configurator`: Helps build new agents.

### 🛠️ Core Specialists
*   `@code-archaeologist`: Expert at digging through legacy code to understand undocumented systems.
*   `@performance-optimizer`: Analyzes code for bottlenecks and memory leaks.
*   `@documentation-specialist`: Generates high-quality API docs and READMEs.

### 🌐 Universal Developers (Framework Agnostic)
*   `@backend-developer`, `@frontend-developer`, `@api-architect`, `@tailwind-css-expert`

### 🐍 Python / Django Experts
*   `@python-expert`, `@fastapi-expert`, `@django-expert`
*   `@django-backend-expert`, `@django-api-developer`, `@django-orm-expert`
*   `@ml-data-expert`, `@web-scraping-expert`
*   `@testing-expert`, `@security-expert`, `@devops-cicd-expert`

### ⚛️ Frontend Framework Experts
*   `@react-component-architect`, `@react-nextjs-expert`
*   `@vue-component-architect`, `@vue-nuxt-expert`, `@vue-state-manager`

### 🐘 PHP / 💎 Ruby Experts
*   `@laravel-backend-expert`, `@laravel-eloquent-expert`
*   `@rails-backend-expert`, `@rails-api-developer`, `@rails-activerecord-expert`

---

## Available Skills

Skills are located in the `.gemini/skills/` directory.

*   **`code-reviewer`**: Runs a rigorous, security-aware review on code changes, outputs a severity-tagged report, and routes major issues to performance or security agents.

---

## How to Add Your Own Agents

1. Create a new markdown file in `.gemini/agents/` (e.g., `my-new-expert.md`).
2. Add YAML frontmatter with a slugified `name` and `description`:
   ```markdown
   ---
   name: my-new-expert
   description: Expert in writing obscure Bash one-liners.
   model: gemini-2.0-flash
   ---
   You are an expert in...
   ```
3. Restart your Gemini CLI session. You can now use `@my-new-expert`!
