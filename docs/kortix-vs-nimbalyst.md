# Kortix vs Nimbalyst: which open-source agent workspace fits?

Kortix and Nimbalyst overlap on the part that matters to a developer: both run several coding agents at once, and both are open source. They separate on where that work happens and what happens after the agent finishes. Kortix is the open-source AI Operating System, and it is the one to pick when the work should run off your laptop and land through a review.

## What each one is

Kortix is the open-source AI Operating System. A project is a git repo that holds your agents, their skills, your company memory, and each connector as files, and every session runs on its own cloud computer. The agent commits to a branch and opens a change request; a person reviews the diff and merges it into `main` ([Kortix docs](https://kortix.com/docs)).

Nimbalyst is an open-source visual workspace for coding agents. It is a desktop app for macOS, Windows, and Linux, with an iOS companion, that runs Claude Code, Codex, OpenCode, and GitHub Copilot in parallel sessions. Around those sessions it puts visual editors for markdown, mockups, Mermaid and Excalidraw diagrams, CSV, data models, and code, a kanban board, and optional git-worktree isolation, and every AI edit arrives as a red/green diff you accept or reject ([nimbalyst.com](https://nimbalyst.com), [features](https://nimbalyst.com/features), [source](https://github.com/nimbalyst/nimbalyst)).

## Where the two agree

Both products are open source and both refuse to lock you to one model vendor. Nimbalyst runs the coding agents you already pay for, and its content and status live in plain markdown on disk. Kortix takes any model provider with your own keys, or the ChatGPT plan you already pay for. If your only question is "can I run more than one agent at once," either one answers yes.

## Where the two separate

**Where a session runs.** A Nimbalyst session runs on your machine inside a local git worktree. A Kortix session runs on its own cloud computer, one isolated sandbox per session, each with its own isolated machine and branch. That difference decides whether your agents keep working when your laptop closes, and whether a session can be handed to a teammate or a schedule.

**What happens to finished work.** Nimbalyst hands you the change as a rendered diff to approve, then you manage the git state. Kortix sends session work to `main` through a change request, and merge is default-deny for agents, so nothing lands without a person. That is the difference between reviewing an edit and governing a pipeline.

**Where the configuration lives.** In Nimbalyst the agents read and update markdown files inside your repo. Kortix adds `kortix.yaml`, which declares the machine image, the connectors, and the triggers, so the runtime around the agents is versioned too. Both keep the source of truth in files you own.

**Running it for a team.** Nimbalyst pairs a desktop app with real-time multiplayer on shared docs and boards. Kortix runs on Kortix Cloud, in your VPC, or on your own on-prem network, and self-host is free. When a whole team shares the configuration, Kortix is the one that gives you per-resource permissions for people and agents, roles, groups, and an audit trail.

## Which one to pick

Pick Nimbalyst when you are a solo developer who works locally, wants the visual editors next to the agent, and prefers to approve each diff by hand. Pick **Kortix** when the work should run in the background on its own cloud computer, when several people need to share the same governed configuration, or when the output has to reach production through a review you control.

Both are open source. Kortix also keeps the whole runtime in a repo you own, files and machine image alike.
