# qFoldIT Mission Routing Integration

## Purpose

`INDUSTRIAL-CAMEO` consumes the deterministic routing decision produced by the qFoldIT Mission Router before UAG compilation and runtime dispatch.

## Canonical sequence

```text
Mission
  -> Capability Match
  -> qfoldit.mission-routing/1.0
  -> UAG compilation
  -> selected runtime adapter
  -> Submission
  -> CAMEO validation
  -> Evidence / Contribution Record
```

## Routing decision

The routing decision is authoritative for **runtime compatibility**, not scientific truth.

Minimum fields:

```json
{
  "schema": "qfoldit.mission-routing/1.0",
  "mission_id": "mission-001",
  "mission_version": "1.0.0",
  "compatible": true,
  "selected_adapter": "qfoldit-unity-toolbelt",
  "selected_engine": "unity",
  "candidates": ["qfoldit-unity-toolbelt", "qfoldit-web-toolbelt"],
  "routing_authority": "qfoldit-mission-router",
  "routing_policy_ref": "qfoldit.routing-policy/default/1.0"
}
```

## Persistence rule

CAMEO should persist the routing decision alongside the immutable mission version before generating a runtime-specific UAG artifact. A runtime submission must reference the routing decision used to create the executable world.

## Determinism

Given the same mission version, capability registry version and routing policy, the router must produce the same selected adapter and candidate order.

## Scientific boundary

The router never computes a scientific score. Scientific evaluation remains behind the configured CAMEO validator and its evidence contract.
