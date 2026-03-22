<p align="center">
<img src="./assets/logo-big-circle.svg" alt="Amadla logo" width="400">
</p>

<h2>About</h2>

> **Alpha — actively under development**

Amadla is an infrastructure automation ecosystem that simplifies provisioning of servers — from a single laptop to a fleet of cloud instances. It works on Linux, macOS, Windows, and OpenBSD.

Most infrastructure tools are **environment-centric**: settings live near the environment, and requirements are scattered across documentation and tribal knowledge. Amadla inverts this to be **resource-centric** — each resource carries its own schema-validated configuration. The same entity that describes an application drives every tool in the chain, from provisioning to validation.

<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/AmadlaOrg/.github/master/profile/assets/amadla_concept_black.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/AmadlaOrg/.github/master/profile/assets/amadla_concept_white.png">
  <img src="https://raw.githubusercontent.com/AmadlaOrg/.github/master/profile/assets/amadla_concept_white.png" alt="Traditional vs Amadla — config imposed top-down vs requirements bubble up via .hery contracts"/>
</picture>
</p>

Amadla is best suited for **1–20 servers**, where it provides production-grade high availability with a fraction of the complexity and overhead of tools like Kubernetes.

<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/AmadlaOrg/.github/master/assets/amadla_venn_black.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/AmadlaOrg/.github/master/assets/amadla_venn_white.png">
  <img src="https://raw.githubusercontent.com/AmadlaOrg/.github/master/assets/amadla_venn_white.png" alt="Amadla Venn Diagram — Amadla at the intersection of Configuration Management, Infrastructure as Code, Image Building, and Secrets Management"/>
</picture>
</p>

<h2>How It Works</h2>

Amadla follows the UNIX philosophy: small, focused CLI tools that each do one thing well and communicate via stdin/stdout with structured data. You can replace, skip, or extend any tool in the chain.

Configuration is defined using [HERY](https://github.com/AmadlaOrg/hery) (Hierarchical Entity Relational YAML) — structured, schema-validated YAML files stored in Git. Entities describe your desired state and can reference and inherit from each other through deep merge. For example, a networking entity attached to an application can inform the HTTP server and automatically open the right firewall ports.

The pipeline flows through these stages:

- **[hery](https://github.com/AmadlaOrg/hery)** — Define and query entity configurations
- **[doorman](https://github.com/AmadlaOrg/doorman)** — Resolve secrets (Vault, AWS, KeePassXC, and more)
- **[raise](https://github.com/AmadlaOrg/raise)** — Provision infrastructure (VMs, cloud instances)
- **[lay](https://github.com/AmadlaOrg/lay)** — Install packages, applications, and language runtimes
- **[enjoin](https://github.com/AmadlaOrg/enjoin)** — Configure system state (users, services, cron, security)
- **[weaver](https://github.com/AmadlaOrg/weaver)** — Generate configuration files from templates
- **[judge](https://github.com/AmadlaOrg/judge)** — Validate and audit the result

<h2>All Tools</h2>

| Tool | Role |
|------|------|
| 🐇 **[amadla](https://github.com/AmadlaOrg/amadla)** | Orchestrator — executes Pipeline entities, coordinates the ecosystem |
| 🐻 **[hery](https://github.com/AmadlaOrg/hery)** | Data storage — entity management with schema validation, Git versioning, SQLite caching |
| 🚪 **[doorman](https://github.com/AmadlaOrg/doorman)** | Secrets management — resolves secrets from pluggable backends (Vault, AWS, KeePassXC, etc.) |
| 🏗️ **[raise](https://github.com/AmadlaOrg/raise)** | Infrastructure provisioner — provisions VMs and cloud resources via plugins |
| 📥 **[lay](https://github.com/AmadlaOrg/lay)** | Installer — installs packages, applications, and language runtimes |
| 🤝 **[enjoin](https://github.com/AmadlaOrg/enjoin)** | System configurator — manages users, services, cron, firewall, security |
| 🧶 **[weaver](https://github.com/AmadlaOrg/weaver)** | Template generator — renders config files using pluggable template engines |
| 🧑‍⚖️ **[judge](https://github.com/AmadlaOrg/judge)** | Validator — checks requirements, cross-entity conflicts, and drift detection |
| 🔬 **[unravel](https://github.com/AmadlaOrg/unravel)** | Discovery — discovers existing system state and outputs it as entities |
| 🍽️ **[waiter](https://github.com/AmadlaOrg/waiter)** | Deployment — blue-green, canary, and rolling deployment strategies |
| 🐙 **[conduct](https://github.com/AmadlaOrg/conduct)** | Multi-server orchestration — coordinates tools across distributed nodes |
| 💨 **[dryrun](https://github.com/AmadlaOrg/dryrun)** | Safe testing — tests settings with auto-revert (e.g., prevents SSH lockout) |
| ⛯ **[lighthouse](https://github.com/AmadlaOrg/lighthouse)** | Notifications — alerting via webhook, SMS, email, and REST API plugins |
| 🗑 **[garbage](https://github.com/AmadlaOrg/garbage)** | Cleanup — tracks and removes what's no longer needed |

<h2>Get Started</h2>

- **[amadla](https://github.com/AmadlaOrg/amadla)** — The orchestrator CLI
- **[Documentation](https://amadla.org/)** — Architecture, concepts, and guides
