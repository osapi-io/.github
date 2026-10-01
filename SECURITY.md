# Security

This file covers every repository in [osapi-io](https://github.com/osapi-io).

## Reporting a vulnerability

Report it privately, not as an issue. Open the Security tab on the repository
the bug is in and use **Report a vulnerability**, which opens a private draft
advisory that only the maintainers can see:

https://github.com/osapi-io/osapi/security/advisories/new

Include what you did, what happened, and what you expected. A proof of concept
helps, but do not run one against a host you do not own.

Expect an acknowledgement within a week. These are small projects with a small
number of maintainers, so a fix may take longer than the acknowledgement does.
We will tell you where it stands rather than leaving the report silent.

When a fix ships, the draft advisory is published with a CVE and you are
credited unless you ask not to be.

## What is supported

The latest release of each repository. There are no maintained release branches,
so a fix lands on `main` and goes out in the next release rather than being
backported.

## What is in scope

The code in these repositories, and the container images published from them.

Out of scope: anything about how you have deployed or configured OSAPI on your
own hosts, and findings from an automated scanner pasted in without a reachable
path through the code. OSAPI runs privileged operations on the machines it
manages by design. An agent being able to change the hostname of the host it
runs on is the product working, not a vulnerability.
