# flockchain-setup handover guide

## Purpose and source

Public installer and release distribution files for the remote-node software.

Reviewed source ref: `c6918b1dc30d165554c5c61db8ba3b0f186c942d`; default branch: `main`. No staging image-to-source mapping was established for this repository.

## Prerequisites and setup

A supported target operating system and the matching release asset.

Use [INSTALLATION.md](https://github.com/Ostrich-AI/flockchain-setup/blob/c6918b1dc30d165554c5c61db8ba3b0f186c942d/INSTALLATION.md) and the release-specific package/checksum record. This repository distributes binaries; source builds are performed in the remote-node repository. Signing, provenance and independent installation verification remain open.

## Configuration

Use the source settings/Helm configuration and existing guides below. A complete environment-variable contract has not been independently established.

## Tests and verification

Test dependencies or files in source are not evidence of a passing run. See source test folders/workflows for declared commands.

Run appropriate tests in an isolated environment with approved configuration and keep the run URL, source ref and results. Some declared lint/test scripts modify files or clean caches; inspect before executing.

## Deployment and rollback

Review Dockerfiles, workflows and the owner-confirmed GitOps/IaC source. Record image digest, environment, migration revision, smoke checks and rollback limitation. Deployment credentials, cloud state and data restoration are outside a Git-only source checkout. Do not run reset/drop/re-index actions against live systems from a copied example.

## Recovery and continuity

Before handover acceptance, verify source/dependency availability, company administration, secret custody, data/config backups and a tested restore. A new engineer must demonstrate setup and a representative journey without undocumented vendor assistance. Record unresolved steps with named owner/date.

## Exact questions to close

1. Is the source/ref above the correct supported version? If different, provide its repository and commit.
2. Which configured image is running now? Provide the image digest and environment.
3. Which documented setup/rollback/restore step has been demonstrated most recently? Link the existing evidence.
4. Which dependencies or accounts remain under vendor control?

## Existing evidence

- [INSTALLATION.md](https://github.com/Ostrich-AI/flockchain-setup/blob/c6918b1dc30d165554c5c61db8ba3b0f186c942d/INSTALLATION.md)
- [README.md](https://github.com/Ostrich-AI/flockchain-setup/blob/c6918b1dc30d165554c5c61db8ba3b0f186c942d/README.md)
