# qFoldIT INDUSTRIAL-CAMEO IP Boundary

## Platform role

INDUSTRIAL-CAMEO is the mission-orchestration boundary between enterprise control, canonical qFoldIT contracts, runtime adapters and scientific validation services.

## Corporate boundary

Production orchestration logic, customer-specific mission policies, private deployment configuration, confidential customer workflows and non-public commercial integrations belong to the qFoldIT corporate surface.

## Public source boundary

Any code already released under an open-source license remains governed by that license for copies already conveyed. This document does not revoke or rewrite previously granted open-source rights.

## Intended repository state

For production corporate orchestration, the qFoldIT organization should operate the production repository as a private corporate repository and expose only intentionally published interfaces, schemas, examples and documentation through public surfaces.

## Evidence

Every production release must record repository, commit SHA, author, review reference, release tag, artifact hashes, dependency/license snapshot and qFoldIT IP evidence registry version.

## Separation of responsibility

- `CORPORATE_APP` owns enterprise control and policy.
- `INDUSTRIAL-CAMEO` owns mission orchestration.
- `OPENSTRUCTURE` owns structural scientific validation.
- Runtime Toolbelts own engine execution.
- `CAMEO-REALTIME-VALIDATION` owns realtime submission/reconciliation.

## Confidentiality

Do not commit secrets, protected scientific references, customer data or credentials. Store confidential assets in the private infrastructure boundary.
