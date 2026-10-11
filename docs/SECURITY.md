# REID v9.3 Security Policy
Consolidated Engineering Edition

============================================================
## 1. Purpose
============================================================

This document defines the security policy for the REID v9.3 architecture.
It provides guidance for reporting vulnerabilities, handling security
incidents, and maintaining safe operation of REID-compliant systems.

Security is a core requirement of REID. All implementations must preserve
identity integrity, temporal monotonicity, drift ceilings, coherence floors,
and governance boundaries defined in the PACK suite.

============================================================
## 2. Reporting Security Issues
============================================================

If you discover a security issue, you must report it privately.

Do not open a public GitHub issue.

Instead, contact the maintainer directly using the information provided
in the LICENSE file.

Provide the following information:

- Description of the issue
- Steps to reproduce
- Impact assessment
- Relevant logs or packet traces
- Suggested mitigation (optional)

All reports will be acknowledged within a reasonable timeframe.

============================================================
## 3. Supported Versions
============================================================

The following versions are actively supported for security updates:

- REID v9.3 (current)
- REID v9.2 (limited support)

Older versions are not maintained.

============================================================
## 4. Security Requirements
============================================================

Implementations must enforce:

- SIL-v9.3 synthesis lock
- AAG-v9.3 governance directives
- ATS-v9.3 packet ordering rules
- Drift ceilings
- Coherence floors
- Epoch monotonicity
- Binding Chain traversal
- Schema alignment

Failure to enforce these requirements may result in unsafe behavior.

============================================================
## 5. Security Boundaries
============================================================

The following boundaries must be respected:

- No bypass of SIL-v9.3
- No override of AAG directives
- No modification of epoch_id
- No alteration of identity-lock headers
- No skipping of Binding Chain layers
- No emission of malformed packets
- No unauthorized synthesis

============================================================
## 6. Vulnerability Classes
============================================================

### Class 1 - Critical
- Epoch regression
- SIL-state mismatch
- AAG directive violation
- Drift ceiling breach
- Coherence floor breach
- ATS ordering violation

### Class 2 - High
- Schema mismatch
- Minor drift/coherence violations
- Non-critical governance faults

### Class 3 - Medium
- Telemetry gaps
- Latency ceiling violations

### Class 4 - Low
- Documentation inconsistencies
- Non-impacting metadata issues

============================================================
## 7. Security Incident Response
============================================================

If a security incident occurs:

1. Suspend synthesis.
2. Activate deterministic fallback.
3. Log event to ATS-v9.3.
4. Capture state snapshot.
5. Notify maintainer.
6. Begin remediation.

============================================================
## 8. Disclosure Policy
============================================================

Security issues will be disclosed publicly only after:

- A fix is available, or
- A mitigation is documented, or
- The issue is determined to be non-exploitable.

============================================================
## 9. Summary
============================================================

This security policy defines the mandatory requirements for safe operation
of REID v9.3 systems. All implementations must follow these rules to ensure
identity integrity, temporal stability, and synthesis safety.

End of Security Policy.
