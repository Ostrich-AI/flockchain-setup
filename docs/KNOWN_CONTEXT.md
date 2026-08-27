# Known Repository Context — FlockChain Setup

**Status:** Working baseline — release and product-owner validation required  
**Classification:** Public utility documentation; internal operational evidence must remain elsewhere

## Purpose

Public installer and onboarding utility for registering supported computers as FlockChain remote nodes.

## Why it exists

Hardware owners must be able to download the utility directly when onboarding a computer to the FlockChain network. Public visibility is intentional and is not a repository-governance defect.

## Product and UAT context

Relevant UAT evidence covers utility downloads, installation, Windows warnings, incorrect filenames, application launch, author/publisher metadata and GitHub/CORS behaviour.

## Adjacent repositories

- `remote-node`
- `ostrich-remote-node-benchmarking`
- `ostrich-flockchain`
- `ostrich-flockchain-dashboard`
- `benchmark-binaries` (archived)

## Public documentation required

- Supported platforms and prerequisites
- Versioned download/install instructions
- Source-to-binary relationship
- Release notes and compatibility
- Checksums/signing/provenance where implemented
- Upgrade, rollback and uninstall
- Network permissions and telemetry disclosure
- Support and vulnerability-reporting channels
- Third-party licences

## Owner validation required

1. Confirm the authoritative release/download mechanism.
2. Correct filenames, product naming, publisher/author metadata and installation UX.
3. Validate CORS/download behaviour from the product interface.
4. Link each published artefact to a source commit and build evidence.
5. Confirm no credentials, customer data or protected VaultNest Core IP are distributed.
6. Link UAT IDs, release, tests and retest evidence.
