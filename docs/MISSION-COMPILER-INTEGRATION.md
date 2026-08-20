# qFoldIT Mission Compiler Integration

## Purpose

`INDUSTRIAL-CAMEO` consumes the output of the qFoldIT Mission Compiler after deterministic runtime selection.

## Canonical flow

```text
qfoldit.mission/1.0
        |
        v
Capability Router
        |
        v
qfoldit.mission-routing/1.0
        |
        v
Mission Compiler
        |
        v
qfoldit.uag/1.0
+
qfoldit.mission-compiled/1.0
        |
        v
Engine Adapter
        |
        v
Runtime Submission
        |
        v
CAMEO Validation
        |
        v
Scientific Evidence
```

## Responsibility boundaries

- `CORPORATE_APP/router` selects a compatible runtime.
- `CORPORATE_APP/compiler` produces the engine-neutral scientific world package.
- UEFN, Unity, UNIGINE and Web adapters realize the package.
- `INDUSTRIAL-CAMEO` routes the submission into the appropriate validation policy.
- Scientific validators remain authoritative for scientific evidence.

## Provenance

The compiled package carries mission identity, routing identity, contract versions, selected runtime and compiler provenance. CAMEO should retain these references in the mission execution record so runtime results remain reproducible.
