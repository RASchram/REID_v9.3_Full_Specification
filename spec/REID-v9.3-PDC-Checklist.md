# REID v9.3 Pre-Flight Checklist (PDC-01 through PDC-15)
Version: v9.3
Epoch: REID-EPOCH-v9.3-2026.10.11-EDT
Registry KID: REID-FULL-9.3-SPEC-2026.10.11-0001
Status: REID v9.3 Documentation

This document defines the mandatory pre-flight checks required before any REID v9.3 deployment, activation, or go-live event. All checks must PASS in a single run. CONDITIONAL results are not accepted.

Each check enforces identity integrity, infrastructure readiness, drift physics, coherence floors, SIL-v9.3 readiness, and baseline alignment.

## PDC Checklist Summary
All 15 checks must be executed in numerical order:

PDC-01: Epoch Verification  
PDC-02: Kubernetes Version Check  
PDC-03: Infrastructure Coherence Baseline  
PDC-04: AAG-v9.3 Connectivity  
PDC-05: Azure Policy Baseline  
PDC-06: SIL Registry Availability  
PDC-07: Temporal Ledger Integrity  
PDC-08: Homestead Latency  
PDC-09: Drift Baseline Alignment  
PDC-10: Identity Baseline (RIG v9.3)  
PDC-11: Corpus Baseline (Corpus v9.3)  
PDC-12: Defender for Cloud Coverage  
PDC-13: Registry KID Format  
PDC-14: SIL Infrastructure Readiness  
PDC-15: Lineage Tag Verification

## PDC-01: Epoch Verification
Requirement:
Active epoch must equal REID-EPOCH-v9.3-2026.10.11-EDT across all subscriptions.

Failure Action:
Block deployment; epoch re-sync required.

## PDC-02: Kubernetes Version Check
Requirement:
AKS cluster must run Kubernetes 1.32.x.

Failure Action:
Block deployment; upgrade required.

## PDC-03: Infrastructure Coherence Baseline
Requirement:
Infrastructure coherence must be >= 0.92.

Failure Action:
Block deployment; enter CE-03 correction cycle.

## PDC-04: AAG-v9.3 Connectivity
Requirement:
AAG-INGEST and AAG-DIRECTIVE channels must respond within 5 seconds.

Failure Action:
Block deployment; reconnect required.

## PDC-05: Azure Policy Baseline
Requirement:
REID-v9.3-Baseline Azure Policy initiative must be applied and compliant.

Failure Action:
Block deployment; policy remediation required.

## PDC-06: SIL Registry Availability
Requirement:
SIL-v9.3 lock hash registry must be reachable; Key Vault keys must be current.

Failure Action:
Block deployment; SIL registry remediation required.

## PDC-07: Temporal Ledger Integrity
Requirement:
ATS v9.3 Temporal Ledger must be writable; GRS replication lag <= 1 minute.

Failure Action:
Block deployment; ledger remediation required.

## PDC-08: Homestead Latency
Requirement:
HMST-01 and HMST-02 round-trip latency to East US 2 must be <= 35ms.

Failure Action:
Advisory only; AUTONOMY-RULE-06 pre-armed.

## PDC-09: Drift Baseline Alignment
Requirement:
EAS v9.3 drift baseline must be active; drift ceilings must be met:
CD <= 0.10  
ED <= 0.05  
XD <= 0.03  
TD <= 0.01

Failure Action:
Block deployment; baseline re-activation required.

## PDC-10: Identity Baseline (RIG v9.3)
Requirement:
RIG v9.3 identity baseline must be active and co-epoch-aligned.

Failure Action:
Block deployment; RIG v9.3 re-activation required.

## PDC-11: Corpus Baseline (Corpus v9.3)
Requirement:
Corpus v9.3 baseline must be active and co-epoch-aligned.

Failure Action:
Block deployment.

## PDC-12: Defender for Cloud Coverage
Requirement:
All subscriptions must be enrolled in Defender for Cloud Enhanced; Sentinel workspace must receive events.

Failure Action:
Block deployment; Defender remediation required.

## PDC-13: Registry KID Format
Requirement:
All active Registry KIDs must match v9.3 format:
REID-[PACK]-9.3-[DOMAIN]-2026.10.11-[SEQ]

Failure Action:
Block deployment; KID correction required.

## PDC-14: SIL Infrastructure Readiness
Requirement:
Infrastructure must enforce SIL-v9.3 lock state on all corpus-carrying payloads.

Failure Action:
Block deployment; SIL infrastructure configuration required.

## PDC-15: Lineage Tag Verification
Requirement:
All deployment manifests must carry lineage tag:
v8.2b -> v9.0 -> v9.1 -> v9.2 -> v9.3

Failure Action:
Block deployment; lineage update required.

## Summary
All 15 PDC checks must PASS in the same run.  
Any failure blocks deployment.  
No REID v9.3 workload may activate until all checks succeed.

End of REID v9.3 Pre-Flight Checklist
