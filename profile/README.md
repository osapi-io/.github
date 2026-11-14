<p align="center">
  <picture>
    <source srcset="https://raw.githubusercontent.com/osapi-io/.github/main/profile/asset/logo-dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset="https://raw.githubusercontent.com/osapi-io/.github/main/profile/asset/logo-light.svg" media="(prefers-color-scheme: light)">
    <img src="https://raw.githubusercontent.com/osapi-io/.github/main/profile/asset/logo-dark.svg" alt="osapi-io" width="360">
  </picture>
</p>

<p align="center">An API that manages Linux hosts and runs each job asynchronously over NATS JetStream.</p>

<p align="center">
  <a href="https://osapi-io.github.io/osapi"><img alt="documentation" src="https://img.shields.io/badge/docs-osapi--io.github.io-blue?style=for-the-badge"></a>
  <a href="https://github.com/osapi-io/osapi/releases/latest"><img alt="release" src="https://img.shields.io/github/release/osapi-io/osapi.svg?style=for-the-badge"></a>
  <a href="https://github.com/osapi-io/osapi/pkgs/container/osapi"><img alt="ghcr.io" src="https://img.shields.io/badge/ghcr.io-osapi-blue?style=for-the-badge&logo=docker&logoColor=white"></a>
  <img alt="go" src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white">
  <img alt="linux" src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black">
  <a href="https://github.com/osapi-io/.github/blob/main/LICENSE"><img alt="license" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=for-the-badge"></a>
</p>

<p align="center">
<b>The controller puts each job on a queue. It does not call the host.</b>
</p>

## What this is

OSAPI makes a Linux host operate like an appliance. One binary and one
configuration file give you a REST API, a CLI, a Go SDK and an embedded
dashboard. They manage a fleet of hosts, not only one host. They control these
parts of each host:

- hostname, DNS, disk, memory and load
- packages, services, users, sysctl and cron
- certificates, containers, files and command execution

```
CLI / SDK / UI  ->  Controller (REST API)  ->  NATS JetStream  ->  Agents
```

The controller never changes the operating system. It writes a job and waits.
An agent on the managed host receives the job. Then a provider on that host
does the work. Delivery is at-least-once, so each provider must be safe to run
two times. The remainder of the design follows from this constraint.

A job can go to:

- one host, by its name
- all hosts in the fleet, as a broadcast
- any one free agent, for load balance
- the hosts that have a given label

## Repositories

| Project | Release | Stars | Description |
|---------|---------|-------|-------------|
| [**osapi**](https://github.com/osapi-io/osapi) | [![release](https://img.shields.io/github/release/osapi-io/osapi.svg?style=for-the-badge)](https://github.com/osapi-io/osapi/releases/latest) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi?style=for-the-badge)](https://github.com/osapi-io/osapi/stargazers) | The controller, the agent, the CLI, the SDK and the embedded dashboard |
| [**osapi-orchestrator**](https://github.com/osapi-io/osapi-orchestrator) | [![release](https://img.shields.io/github/release/osapi-io/osapi-orchestrator.svg?style=for-the-badge)](https://github.com/osapi-io/osapi-orchestrator/releases/latest) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi-orchestrator?style=for-the-badge)](https://github.com/osapi-io/osapi-orchestrator/stargazers) | Runs multi-step operations across OSAPI-managed hosts |
| [**gohai**](https://github.com/osapi-io/gohai) | [![release](https://img.shields.io/github/release/osapi-io/gohai.svg?style=for-the-badge)](https://github.com/osapi-io/gohai/releases/latest) | [![stars](https://img.shields.io/github/stars/osapi-io/gohai?style=for-the-badge)](https://github.com/osapi-io/gohai/stargazers) | Collects system facts, like Chef Ohai |
| [**nats-client**](https://github.com/osapi-io/nats-client) | [![release](https://img.shields.io/github/release/osapi-io/nats-client.svg?style=for-the-badge)](https://github.com/osapi-io/nats-client/releases/latest) | [![stars](https://img.shields.io/github/stars/osapi-io/nats-client?style=for-the-badge)](https://github.com/osapi-io/nats-client/stargazers) | Connects to NATS and JetStream |
| [**nats-server**](https://github.com/osapi-io/nats-server) | [![release](https://img.shields.io/github/release/osapi-io/nats-server.svg?style=for-the-badge)](https://github.com/osapi-io/nats-server/releases/latest) | [![stars](https://img.shields.io/github/stars/osapi-io/nats-server?style=for-the-badge)](https://github.com/osapi-io/nats-server/stargazers) | Runs a NATS server inside a Go process |
| [**osapi-justfiles**](https://github.com/osapi-io/osapi-justfiles) | [![release](https://img.shields.io/badge/release-main-lightgrey?style=for-the-badge)](https://github.com/osapi-io/osapi-justfiles/commits/main) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi-justfiles?style=for-the-badge)](https://github.com/osapi-io/osapi-justfiles/stargazers) | The `just` recipes that every repository here imports |
| [**specs**](https://github.com/osapi-io/specs) | [![release](https://img.shields.io/badge/release-living-lightgrey?style=for-the-badge)](https://github.com/osapi-io/specs/commits/main) | [![stars](https://img.shields.io/github/stars/osapi-io/specs?style=for-the-badge)](https://github.com/osapi-io/specs/stargazers) | The design docs, written before the code |
| [**osapi-lab**](https://github.com/osapi-io/osapi-lab) | [![release](https://img.shields.io/badge/release-main-lightgrey?style=for-the-badge)](https://github.com/osapi-io/osapi-lab/commits/main) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi-lab?style=for-the-badge)](https://github.com/osapi-io/osapi-lab/stargazers) | Tart VMs on a Mac that run an osapi branch across real distributions |

Start with [osapi](https://github.com/osapi-io/osapi). Each other repository
is a library that osapi imports, or a tool that reads osapi.

## How we do the work

Design comes first. A change starts as a page in [specs](https://github.com/osapi-io/specs).
Then we build the change. Then we correct the page where the build showed that
the design was wrong. It is one page in all three steps. We do not convert it
from one form into another. Thus the design and the documentation always agree.

## Try it

```bash
# run the controller, the agent and NATS together
osapi start

# ask one host its hostname
osapi client node hostname --target web-01

# ask every host for its users
osapi client node user list --target _all

# open the dashboard
open http://localhost:8080
```

[Documentation](https://osapi-io.github.io/osapi) |
[API reference](https://osapi-io.github.io/osapi/category/api) |
[Contributing](https://osapi-io.github.io/osapi/sidebar/development/contributing) |
[Security](https://github.com/osapi-io/.github/blob/main/SECURITY.md) |
[Code of conduct](https://github.com/osapi-io/.github/blob/main/CODE_OF_CONDUCT.md) |
[AI policy](https://github.com/osapi-io/.github/blob/main/AI_POLICY.md)
