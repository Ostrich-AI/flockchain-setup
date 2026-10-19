# Repository Profile — `Ostrich-AI/flockchain-setup`

**Documentation status:** Draft — SME validation required  
**Working/default branch reviewed:** `main`  
**Documentation branch:** `docs/repository-governance-2026-08`  
**Visibility:** Public — intentional  
**Classification:** Public distribution repository; operational internals and credentials remain restricted  
**Central worklist:** [Engineering Governance Readiness](https://github.com/Ostrich-AI/ostrich-system-blueprints/blob/main/ENGINEERING_GOVERNANCE_READINESS.md)

## Confirmed business decision

This repository is intentionally public so that a person onboarding a computer as a FlockChain remote node can download the required utility directly from GitHub.

Public visibility is therefore not a defect. The remaining governance objective is to make distribution, integrity, compatibility, support and update behaviour clear and safe.

## Purpose and lifecycle

- Utility purpose and supported onboarding journey: `[OSTRICH FLOCKCHAIN PRODUCT OWNER TO CONFIRM]`
- Source-to-binary relationship: `[SMARTSENSE NODE/RELEASE OWNER TO COMPLETE]`
- Supported platforms/versions: `[SMARTSENSE QA/NODE OWNER TO COMPLETE]`
- Release/support lifecycle: `[PRODUCT AND TECHNICAL OWNERS TO CONFIRM]`

## Owners

| Responsibility | Name or role |
|---|---|
| Product owner | `[OSTRICH FLOCKCHAIN OWNER TO CONFIRM]` |
| Utility/node technical owner | `[SMARTSENSE ENGINEERING LEAD TO ASSIGN]` |
| Release/package owner | `[SMARTSENSE DEVOPS LEAD TO ASSIGN]` |
| QA/platform owner | `[SMARTSENSE QA LEAD TO ASSIGN]` |
| Security/vulnerability owner | `[OSTRICH SECURITY OWNER TO CONFIRM]` |
| User support owner | `[SERVICE OWNER TO COMPLETE]` |

## Required implementation evidence

1. Document the supported node-onboarding journey and prerequisites.
2. Identify supported operating systems, architectures and hardware requirements.
3. Explain whether users download source, scripts, installers or binaries and how each is built.
4. Publish versioned releases rather than relying only on moving branch files or `latest` artefacts.
5. Provide checksums and, where implemented, signing/provenance verification instructions.
6. Document update, rollback, uninstall and unsupported-version behaviour.
7. State required network destinations, ports and permissions without exposing credentials.
8. Provide vulnerability-reporting, support and incident-escalation routes.
9. Inventory third-party packages, licences and public-distribution obligations.
10. Confirm that no secrets, internal-only endpoints, customer data or protected VaultNest Core material are included.

## Evidence links

| Evidence | Link / owner action |
|---|---|
| User installation guide | `[PRODUCT/TECHNICAL OWNER TO COMPLETE]` |
| Platform compatibility matrix | `[QA OWNER TO COMPLETE]` |
| Release/build pipeline | `[RELEASE OWNER TO COMPLETE]` |
| Checksums/signing/provenance | `[RELEASE/SECURITY OWNER TO COMPLETE]` |
| Update/rollback/uninstall | `[TECHNICAL OWNER TO COMPLETE]` |
| Network and permission requirements | `[TECHNICAL/SECURITY OWNER TO COMPLETE]` |
| Support/vulnerability reporting | `[SUPPORT/SECURITY OWNER TO COMPLETE]` |
| SBOM/licence inventory | `[ENGINEERING/LEGAL OWNER TO COMPLETE]` |

## Public-repository rule

Documentation intended for public users must be concise and safe. Internal infrastructure topology, credentials, private endpoints, customer data, protected IP and administrative procedures belong in restricted records and should be referenced only at an appropriate level.

## Completion sign-off

- Product owner: `[NAME / DATE]`
- Technical owner: `[NAME / DATE]`
- Release owner: `[NAME / DATE]`
- QA owner: `[NAME / DATE]`
- Security/legal owner: `[NAME / DATE]`
