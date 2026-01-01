# repodock

**repodock** analyzes Python GitHub repositories and proposes a reproducible container setup to run the project in an isolated local environment.

The focus is on **understanding, transparency, and risk awareness** — not on magic automation or black-box behavior.

---

## Motivation

Cloning and running an unfamiliar Python repository often fails due to:

- unclear Python version requirements
- implicit system-level dependencies
- missing or undocumented services
- incomplete or outdated setup instructions

`repodock` scans the repository, detects common patterns, and generates a **reasoned container blueprint** — including hints about **where things are likely to break**.

---

## What repodock is

- a **static repository analyzer**
- a generator for:
  - `Dockerfile`
  - optional `docker-compose.yml`
  - an analysis report with risks and assumptions
- a tool for developers who want to **quickly assess** foreign repositories

---

## What repodock is not

- ❌ not a guarantee that the project will run without execution
- ❌ not a deployment tool
- ❌ not a host-level dependency installer
- ❌ not a replacement for documentation or domain knowledge

If a project requires secrets, data, or external systems to work, `repodock` will not hide that fact.

---

## Current status

🟡 **Scaffold / Research phase**

- base structure in place
- detection rules under design
- no stable CLI output yet

This repository is intentionally public early to make scope,
assumptions, and design decisions explicit.

---

## Planned output (target)

After analyzing a repository, `repodock` aims to generate:

- a `Dockerfile` (recommended runtime and system dependencies)
- a `docker-compose.yml` (if services like databases or brokers are detected)
- a `repodock-report.md` containing:
  - detected project structure
  - assumptions made
  - a risk score
  - unresolved items (e.g. env vars, secrets)

---

## Rough roadmap

- **v0.1**
  - static scan
  - Python version detection
  - Dockerfile generation
- **v0.2**
  - service detection
  - docker-compose templates
- **v0.3**
  - optional verify mode (container build/run test)

Details will be tracked in issues.

---

## License

MIT License
