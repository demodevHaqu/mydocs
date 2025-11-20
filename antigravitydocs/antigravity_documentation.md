# Google Antigravity Documentation

This document is a comprehensive summary of the official Google Antigravity documentation, covering its core concepts, features, and usage.

## 1. Introduction

**Google Antigravity** is an agentic development platform that evolves the traditional IDE into an agent-first experience. It enables developers to operate at a higher, task-oriented level by managing agents across workspaces while retaining a familiar AI IDE core.

Key capabilities include:

- **Agentic Workflow**: Extracts agents into their own surface, providing them with tools to autonomously operate across the editor, terminal, and browser.
- **Task-Oriented**: Emphasizes verification and higher-level communication via tasks and artifacts.
- **End-to-End Development**: Enables agents to plan and execute complex software tasks, from building features and UI iteration to bug fixing and research.

### Main Features

- **AI-powered IDE**: Includes features like Agent, Tab, and Command.
- **Asynchronous Agents**: Local agents work in parallel on workspaces.
- **Agent Manager**: A dedicated view for planning, conversation, and artifact review.
- **Multi-window**: Supports Editor, Manager, and Browser windows.

---

## 2. Core Concepts

### Agent

The **Agent** is the core AI functionality within Antigravity. It is a multi-step reasoning system powered by a frontier LLM that can:

- Reason over existing code.
- Use a wide range of tools (including the browser).
- Communicate with the user through tasks, artifacts, and more.

**Core Components:**

- **Reasoning Model**: The underlying LLM driving the agent.
- **Tools**: Capabilities the agent can use (file editing, terminal, browser, etc.).
- **Artifacts**: Outputs created by the agent (plans, code, diagrams).
- **Knowledge**: Persistent memory of insights.
- **Customizations**: User-defined settings and rules.

### Models

Antigravity supports various reasoning models, allowing developers to choose the best fit for their task:

- **Gemini 3 Pro**
- **Claude Sonnet 4.5**
- **GPT-OSS**

### Agent Modes & Settings

The Agent can operate in different modes:

- **Planning Mode**: For complex tasks requiring a structured approach.
- **Fast Mode**: For quick, smaller tasks.

**Settings** include options like the **Artifact Review Policy**, which controls how and when the user reviews agent outputs.

### Task Groups

When in **Planning Mode**, the Agent handles large and complex tasks using **Task Groups**.

- **Breakdown**: Problems are broken down into smaller, approachable units of work.
- **Parallelism**: The Agent can work on multiple parts of a task simultaneously.
- **Presentation**: Task sections present changes to the user, including a summary of the goal and a list of edited files for quick audit.

### Knowledge

**Knowledge Items** act as a persistent memory system. They capture insights, solutions, and context from coding sessions, which are stored and viewable in the Agent Manager. This allows the agent to "learn" from previous tasks.

---

## 3. Editor Experience

The **Editor** is the primary entry point, based on VS Code but enhanced with rich AI features.

### Editor Overview

- **Familiarity**: Designed to feel like standard editors (open files, tab through them, edit directly).
- **AI Integration**: Deeply integrated with Agent, Tab, and Command features.
- **Extensions**: Supports Open VSX marketplace extensions for syntax highlighting, source control, etc.

### Tab & Navigation

- **Supercomplete**: Provides code suggestions near the cursor. It can modify code file-wide (e.g., renaming variables, updating function definitions).
- **Tab-to-Jump**: A fluid navigation tool that suggests the next logical place to move the cursor.
- **Tab-to-Import**: (Implied) Helps with importing modules.

### Command

**Command** brings natural language to the workflow.

- **Trigger**: `Command + I` (Mac) or `Ctrl + I` (Windows/Linux).
- **Usage**: Type a request in natural language (e.g., "Create a function to sort this list").
- **Execution**: Antigravity generates the code or command inline for review.

### Agent Side Panel

Located on the right side of the editor.

- **Function**: Work directly with the agent.
- **Capabilities**: Spin up new conversations, attach images, switch agent modes, select models.
- **Tracking**: Keep track of open file changes, running terminal processes, and artifacts via the bottom toolbar.

### Review Changes + Source Control

- **Review Changes**: A section in the Agent panel's bottom toolbar allows scrolling through all changes made by the agent and user in a conversation.
- **Interaction**: Users can comment on file diffs to communicate feedback to the agent.

---

## 4. Features & Tools

### Browser Subagent

When the agent needs to interact with the web, it uses the **Browser Subagent**.

- **Specialized Model**: Runs a model specialized for browser operations.
- **Capabilities**: Clicking, scrolling, typing, reading console logs, DOM capture, screenshots, markdown parsing, and video recording.
- **Overlay**: Shows a blue border and action panel when controlling a page.
- **Background Operation**: Can work on unfocused tabs, allowing the user to continue working in other tabs.

### MCP (Model Context Protocol)

Antigravity integrates with **MCP**, allowing the editor to connect to local tools and external services. This provides the agent with real-time context and capabilities beyond the immediate codebase.

---

## 5. Artifacts

**Artifacts** are the tangible outputs created by the agent to perform work or communicate.

### Types of Artifacts

- **Task List**: Used to monitor progress on complex tasks.
- **Implementation Plan**: Architects code changes for user review and comment.
- **Walkthrough**: Summarizes changes made, often including screenshots and recordings.
- **Screenshots**: Images captured by the browser subagent.
- **Browser Recordings**: Video recordings of browser subagent actions.
- **Diagrams/Code**: (Implied) Other generated content.

---

## 6. Agent Manager & Workspaces

### Agent Manager

A higher-level view for overseeing agent work.

- **Birds-eye View**: Manage multiple workspaces and dozens of agents simultaneously.
- **Interaction**: Interact with the codebase primarily through the agent.
- **Navigation**: Toggle between Editor and Manager with `CMD+E` / `CTRL+E`.
- **Window Management**: Hide, focus, or close editor windows from the manager.

### Workspaces

- **Multi-Workspace**: Work across multiple workspaces simultaneously in the Agent Manager.
- **Creation**: Open new workspaces by selecting a starting folder.
- **Switching**: Switch between conversations across workspaces via the sidebar.
