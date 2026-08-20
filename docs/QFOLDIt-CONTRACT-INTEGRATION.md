# qFoldIT Contract Integration

INDUSTRIAL-CAMEO is the mission orchestration boundary between enterprise requests, scientific targets, runtime experiences and scientific evaluation.

## Canonical contracts

- `qfoldit.mission/1.0` — mission identity, version and lifecycle.
- `qfoldit.submission/1.0` — runtime candidate returned for evaluation.
- `qfoldit.evidence/1.0` — authoritative scientific assessment.
- `qfoldit.contribution-record/1.0` — durable attribution and reward-eligibility projection.
- `qfoldit.event/1.0` — event envelope used for lifecycle propagation.
- `qfoldit.uag/1.0` — engine-neutral world assembly contract.

## Authority boundaries

```text
Enterprise request
      |
      v
Mission Registry
      |
      v
INDUSTRIAL-CAMEO
      |
      +--> UAG mission compilation
      |
      +--> Runtime Adapter
      |
      +--> Submission normalization
      |
      v
Scientific Validation
      |
      v
Evidence
      |
      +--> Contribution Record
      |
      +--> Reward Policy
      |
      v
STATE projection
```

INDUSTRIAL-CAMEO orchestrates these transitions but does not redefine scientific truth. Scientific scores must originate from the configured validation authority.

## Required implementation behavior

1. Every mission execution is associated with an immutable `missionId` and explicit mission version.
2. Runtime submissions are normalized into `qfoldit.submission/1.0` before validation.
3. Validation responses are normalized into `qfoldit.evidence/1.0`.
4. Reward eligibility is evaluated separately from scientific scoring.
5. Lifecycle changes are emitted as `qfoldit.event/1.0` envelopes.
6. Public projections contain only fields explicitly approved for STATE publication.

## Vertical independence

Biotech, hardware, IoT, energy, mining, materials and future scientific domains use the same orchestration contracts. Domain-specific validators remain replaceable behind the evidence boundary.
