# RDI Development

This branch exists as the mapped Debezium core line for the RDI `debezium-server` release branch.

## Scope

For the RDI `3.5` line:

- server repo: `redislabsdev/debezium-server`
- server branch: `rdi/3.5`
- core repo: `redislabsdev/debezium`
- core branch: `rdi/3.5`

`debezium-server` is built against this core branch by the RDI build workflow. The branch pairing is defined in:

- `debezium-server/.github/rdi-core-mapping.json`

## Primary Workflow

The main local build, image build, CI publishing, and downstream validation loop is documented in the server repo:

- repo-local: `../debezium-server/RDI_DEVELOPMENT.md`
- GitHub: `https://github.com/redislabsdev/debezium-server/blob/rdi/3.5/RDI_DEVELOPMENT.md`

That document covers:

- building the RDI server distribution
- building a local Debezium Server image
- using the image from `redis-data-integration`
- branch builds to Artifactory
- release tags to Docker Hub

## Core Repo Expectations

Changes in this repo should stay focused on the Debezium core line needed by the paired RDI server branch.

In practice, that means:

- keep `rdi/3.5` in sync with the server branch's expected core state
- make functional core changes here only when the RDI server branch actually needs them
- use the server repo doc as the source of truth for the end-to-end RDI development loop
