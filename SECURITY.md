# Security

This file covers every repository in [osapi-io](https://github.com/osapi-io).

## Report a vulnerability

Report the vulnerability privately. Do not open an issue.

1. Open the Security tab of the repository that has the bug.
1. Select **Report a vulnerability**. GitHub opens a private draft advisory.
   Only the maintainers can see the advisory.

   https://github.com/osapi-io/osapi/security/advisories/new

1. Write what you did, what occurred, and what you expected.
1. If you have a proof of concept, include it. Do not run a proof of concept
   against a host that you do not own.

The maintainers acknowledge a report in one week or less. These projects have
few maintainers, so a fix can take more time than the acknowledgement. The
maintainers tell you the status of the fix. They do not leave a report
without an answer.

When the fix is released, the maintainers publish the draft advisory with a
CVE. The advisory gives you credit, unless you ask the maintainers not to.

## What is supported

The maintainers support the latest release of each repository. There are no
maintained release branches. A fix goes into `main` and into the next release.
The maintainers do not backport a fix to an earlier release.

## What is in scope

The code in these repositories is in scope. The container images that the
maintainers publish from these repositories are also in scope.

These are out of scope:

- How you deployed or configured OSAPI on your own hosts.
- A finding from an automated scanner that has no reachable path through the
  code.

OSAPI does privileged operations on the machines that it manages. This is
intentional. When an agent changes the hostname of its host, the product
works correctly. That is not a vulnerability.
