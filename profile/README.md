<div align="center">

<img src="https://raw.githubusercontent.com/osapi-io/osapi/main/asset/logo.png" alt="OSAPI" width="120" />

# OSAPI

**A CRUD API for managing Linux systems**

[![release](https://img.shields.io/github/release/osapi-io/osapi.svg?style=for-the-badge)](https://github.com/osapi-io/osapi/releases/latest)
[![build](https://img.shields.io/github/actions/workflow/status/osapi-io/osapi/go.yml?style=for-the-badge)](https://github.com/osapi-io/osapi/actions/workflows/go.yml)
[![license](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=for-the-badge)](https://github.com/osapi-io/osapi/blob/main/LICENSE)
[![docker](https://img.shields.io/badge/ghcr.io-osapi-blue?style=for-the-badge&logo=docker&logoColor=white)](https://github.com/osapi-io/osapi/pkgs/container/osapi)
![openapi initiative](https://img.shields.io/badge/openapiinitiative-%23000000.svg?style=for-the-badge&logo=openapiinitiative&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

<a href="https://osapi-io.github.io/osapi">Documentation</a> &bull;
<a href="https://osapi-io.github.io/osapi/category/api">API Reference</a> &bull;
<a href="https://osapi-io.github.io/osapi/sidebar/development/contributing">Contributing</a>

</div>

---

OSAPI turns Linux servers into managed appliances. Install a single binary, point
it at a config file, and get a REST API, CLI, and web dashboard for managing
system configuration across your fleet.

### What it does

> Hostname, DNS, disk, memory, users, packages, services, cron, sysctl, NTP,
> certificates, Docker containers, file deploys, process management, network
> interfaces, routes — all through one consistent API with async job processing.

### How it works

```
CLI / SDK / UI  →  Controller (REST API)  →  NATS JetStream  →  Agents
```

The controller never touches the OS directly. It creates jobs routed through NATS
to agents running on each managed host. Target a specific host, broadcast to all,
load-balance across any, or route by labels.

### Repositories

| Project | Stars | Description |
|---------|-------|-------------|
| [**osapi**](https://github.com/osapi-io/osapi) | [![Stars](https://img.shields.io/github/stars/osapi-io/osapi?style=social)](https://github.com/osapi-io/osapi) | Core API server, agent, CLI, and embedded UI |
| [**osapi-orchestrator**](https://github.com/osapi-io/osapi-orchestrator) | [![Stars](https://img.shields.io/github/stars/osapi-io/osapi-orchestrator?style=social)](https://github.com/osapi-io/osapi-orchestrator) | Multi-step operation orchestration engine |
| [**osapi-justfiles**](https://github.com/osapi-io/osapi-justfiles) | [![Stars](https://img.shields.io/github/stars/osapi-io/osapi-justfiles?style=social)](https://github.com/osapi-io/osapi-justfiles) | Shared just recipes for CI and development |
| [**nats-client**](https://github.com/osapi-io/nats-client) | [![Stars](https://img.shields.io/github/stars/osapi-io/nats-client?style=social)](https://github.com/osapi-io/nats-client) | NATS JetStream client library |
| [**nats-server**](https://github.com/osapi-io/nats-server) | [![Stars](https://img.shields.io/github/stars/osapi-io/nats-server?style=social)](https://github.com/osapi-io/nats-server) | Embedded NATS server wrapper |

### Quick start

```bash
# Install and run all three components
osapi start

# Query a host
osapi client node hostname --target web-01

# Broadcast to the fleet
osapi client node user list --target _all

# Open the dashboard
open http://localhost:8080
```
