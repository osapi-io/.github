<p align="center">
  <picture>
    <source srcset="https://raw.githubusercontent.com/osapi-io/.github/main/profile/asset/logo-dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset="https://raw.githubusercontent.com/osapi-io/.github/main/profile/asset/logo-light.svg" media="(prefers-color-scheme: light)">
    <img src="https://raw.githubusercontent.com/osapi-io/.github/main/profile/asset/logo-dark.svg" alt="osapi-io" width="360">
  </picture>
</p>

<p align="center">A Linux system management API with async job processing over NATS JetStream.</p>

<p align="center">
  <a href="https://osapi-io.github.io/osapi"><img alt="documentation" src="https://img.shields.io/badge/docs-osapi--io.github.io-blue?style=for-the-badge"></a>
  <a href="https://github.com/osapi-io/osapi/releases/latest"><img alt="release" src="https://img.shields.io/github/release/osapi-io/osapi.svg?style=for-the-badge"></a>
  <a href="https://github.com/osapi-io/osapi/pkgs/container/osapi"><img alt="ghcr.io" src="https://img.shields.io/badge/ghcr.io-osapi-blue?style=for-the-badge&logo=docker&logoColor=white"></a>
  <img alt="go" src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white">
  <img alt="linux" src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black">
  <a href="https://github.com/osapi-io/osapi/blob/main/LICENSE"><img alt="license" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=for-the-badge"></a>
</p>

<p align="center">
<b>Work reaches a host by being queued, not by being called.</b>
</p>

## What this is

OSAPI makes a Linux host behave like an appliance. One binary and a config file
give you a REST API, a CLI, a Go SDK and an embedded dashboard over hostname,
DNS, disk, memory, load, packages, services, users, sysctl, cron, certificates,
containers, files and command execution, across a fleet rather than one box.

```
CLI / SDK / UI  ->  Controller (REST API)  ->  NATS JetStream  ->  Agents
```

The controller never touches the operating system. It writes a job and waits.
An agent on the managed host picks the job up and a provider does the work.
Delivery is at-least-once, so every provider has to be safe to run twice, and
that constraint is what the rest of the design is built around.

Target one host by name, broadcast to the whole fleet, load-balance across any
free agent, or route by label.

## Repositories

| Project | Release | Stars | Description |
|---------|---------|-------|-------------|
| [**osapi**](https://github.com/osapi-io/osapi) | [![release](https://img.shields.io/badge/release-unreleased-lightgrey?style=for-the-badge)](https://github.com/osapi-io/osapi/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi?style=for-the-badge)](https://github.com/osapi-io/osapi/stargazers) | The controller, the agent, the CLI, the SDK and the embedded dashboard |
| [**osapi-orchestrator**](https://github.com/osapi-io/osapi-orchestrator) | [![release](https://img.shields.io/badge/release-unreleased-lightgrey?style=for-the-badge)](https://github.com/osapi-io/osapi-orchestrator/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi-orchestrator?style=for-the-badge)](https://github.com/osapi-io/osapi-orchestrator/stargazers) | Runs multi-step operations across OSAPI-managed hosts |
| [**gohai**](https://github.com/osapi-io/gohai) | [![release](https://img.shields.io/github/v/tag/osapi-io/gohai?style=for-the-badge&label=release)](https://github.com/osapi-io/gohai/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/gohai?style=for-the-badge)](https://github.com/osapi-io/gohai/stargazers) | Collects system facts, in the spirit of Chef Ohai |
| [**nats-client**](https://github.com/osapi-io/nats-client) | [![release](https://img.shields.io/github/v/tag/osapi-io/nats-client?style=for-the-badge&label=release)](https://github.com/osapi-io/nats-client/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/nats-client?style=for-the-badge)](https://github.com/osapi-io/nats-client/stargazers) | Connects to NATS and JetStream |
| [**nats-server**](https://github.com/osapi-io/nats-server) | [![release](https://img.shields.io/github/v/tag/osapi-io/nats-server?style=for-the-badge&label=release)](https://github.com/osapi-io/nats-server/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/nats-server?style=for-the-badge)](https://github.com/osapi-io/nats-server/stargazers) | Runs a NATS server inside a Go process |
| [**osapi-justfiles**](https://github.com/osapi-io/osapi-justfiles) | [![release](https://img.shields.io/badge/release-tracks%20main-lightgrey?style=for-the-badge)](https://github.com/osapi-io/osapi-justfiles/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/osapi-justfiles?style=for-the-badge)](https://github.com/osapi-io/osapi-justfiles/stargazers) | The `just` recipes every repository here imports |
| [**specs**](https://github.com/osapi-io/specs) | [![release](https://img.shields.io/badge/release-living-lightgrey?style=for-the-badge)](https://github.com/osapi-io/specs/releases) | [![stars](https://img.shields.io/github/stars/osapi-io/specs?style=for-the-badge)](https://github.com/osapi-io/specs/stargazers) | The design docs, written before the code |

Start with [osapi](https://github.com/osapi-io/osapi). Everything else is either
something it imports or something that reads it.

## How the work is done

Design first. A change starts as a page in [specs](https://github.com/osapi-io/specs),
gets built, and then the page is corrected wherever building proved it wrong.
It is the same page all three times, so nothing is converted from one form into
another, and the design and the documentation cannot drift apart.

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
[Security](https://github.com/osapi-io/.github/blob/main/SECURITY.md)
