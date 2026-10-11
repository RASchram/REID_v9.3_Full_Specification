# REID v9.3 Identity Baseline (RIG v9.3)
Version: v9.3
Epoch: REID-EPOCH-v9.3-2026.10.11-EDT
Registry KID: RIG-9.3-BASELINE-2026.10.11-0001
Status: REID v9.3 Documentation

The REID Identity Baseline (RIG v9.3) defines the foundational identity parameters required for all REID v9.3 workloads. RIG v9.3 ensures identity stability, epoch alignment, and PACK-layer consistency.

RIG v9.3 must be active before any REID v9.3 workload is deployed.

## 1. Purpose of RIG v9.3
RIG v9.3 provides:

- Identity substrate initialization
- Epoch alignment
- Registry KID format enforcement
- Identity-Lock Header baseline
- PACK-layer identity consistency
- Drift and coherence baseline alignment

RIG v9.3 is required for all identity-carrying payloads.

## 2. Identity Baseline Fields
RIG v9.3 defines the following mandatory fields:

- Framework: REID
- Version: v9.3
- Epoch: REID-EPOCH-v9.3-2026.10.11-EDT
- Registry KID: RIG-9.3-BASELINE-2026.10.11-0001
- Lineage: v8.2b -> v9.0 -> v9.1 -> v9.2 -> v9.3

These fields must appear in all identity-carrying payloads.

## 3. Identity-Lock Header Requirements
Identity-Lock Header must include:

- Framework name
- Version
- Epoch
- Registry KID
- Lineage
- Identity state
- SIL-state (if applicable)
- Drift and coherence metadata

Any mismatch triggers GF-CLASS-1.

## 4. Drift Baseline Alignment
RIG v9.3 enforces drift ceilings:

- Corpus Drift <= 0.10
- Cross-Domain Drift <= 0.03
- Emergent Drift <= 0.05
- Temporal Drift <= 0.01

Drift values must be recorded in the Temporal Ledger.

## 5. Coherence Baseline Alignment
RIG v9.3 enforces coherence floors:

- Global Coherence >= 0.90
- Infrastructure Coherence >= 0.92

Coherence values must be recorded in the Temporal Ledger.

## 6. Registry KID Format
All identity-carrying payloads must use the v9.3 KID format:

REID-[PACK]-9.3-[DOMAIN]-2026.10.11-[SEQ]

Examples:

- REID-L2-9.3-COG-2026.10.11-0004
- REID-L7-9.3-CORPUS-2026.10.11-0021

Incorrect KID format triggers GF-CLASS-1.

## 7. Epoch Alignment Rules
Epoch must be:

- Monotonic
- Consistent across all PACK layers
- Consistent across all subscriptions
- Consistent across all identity-carrying payloads

Epoch regression triggers GF-CLASS-1.

## 8. RIG v9.3 Activation Requirements
RIG v9.3 must be:

- Active
- Co-epoch-aligned
- Registered in ATS v9.3 Temporal Ledger
- Verified by VXL-1 and VXL-4
- Confirmed by PDC-10

If RIG v9.3 is inactive, all REID v9.3 workloads are blocked.

## 9. RIG v9.3 Failure Modes
Failure modes include:

- Incorrect epoch
- Incorrect KID format
- Missing lineage
- Drift ceiling violation
- Coherence floor violation
- Missing identity fields

All failure modes trigger GF-CLASS-1.

## 10. Summary
RIG v9.3 provides:

- Identity substrate initialization
- Drift and coherence baseline alignment
- Epoch alignment
- Registry KID enforcement
- Identity-Lock Header baseline
- PACK-layer identity consistency

RIG v9.3 is required for all REID v9.3 workloads.

End of RIG v9.3 Identity Baseline
