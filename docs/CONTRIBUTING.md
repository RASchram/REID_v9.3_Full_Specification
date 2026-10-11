# Contributing to REID v9.3
Consolidated Engineering Edition

============================================================
## 1. Purpose
============================================================

This document defines the contribution process for the REID v9.3
architecture. It ensures that all contributions maintain identity
integrity, temporal monotonicity, drift ceilings, coherence floors,
and governance boundaries defined in the PACK suite.

All contributions must align with the REID v9.3 specification and
preserve the Binding Chain.

============================================================
## 2. Contribution Types
============================================================

The following contribution types are accepted:

- Documentation improvements
- Diagram updates
- Schema corrections
- PACK clarifications
- Infrastructure templates
- Non-breaking enhancements
- Governance envelope refinements

The following contributions are not accepted:

- Breaking changes to PACK structure
- Modifications to epoch physics
- Alterations to SIL-v9.3 or AAG-v9.3
- Changes that violate drift or coherence ceilings
- Additions that bypass the Binding Chain

============================================================
## 3. How to Contribute
============================================================

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Ensure all PACK references remain consistent.
5. Validate schema alignment.
6. Run drift and coherence checks if applicable.
7. Submit a pull request.

Pull requests must include:

- Description of the change
- PACKs affected
- Impact assessment
- Conformance verification
- Any diagrams updated

============================================================
## 4. Coding and Documentation Standards
============================================================

All contributions must follow:

- ASCII-only diagrams
- Markdown-only documentation
- Consistent PACK naming
- Consistent epoch references
- Schema alignment with Appendix A and B
- No proprietary engine details
- No breaking changes to governance envelopes

============================================================
## 5. Review Process
============================================================

All contributions undergo the following review steps:

1. Initial review for clarity and alignment.
2. PACK cross-reference validation.
3. Schema consistency check.
4. Governance envelope compliance.
5. Epoch physics verification.
6. Final approval.

If a contribution violates any conformance rule, it will be rejected.

============================================================
## 6. Governance Requirements
============================================================

All contributions must respect:

- SIL-v9.3 synthesis lock
- AAG-v9.3 directives
- ATS-v9.3 ordering rules
- Drift ceilings
- Coherence floors
- Epoch monotonicity
- Binding Chain traversal

These requirements are mandatory.

============================================================
## 7. Security Considerations
============================================================

Contributors must not:

- Introduce bypasses to SIL-v9.3
- Modify AAG directive routing
- Alter identity-lock headers
- Change epoch_id or epoch_sequence rules
- Emit malformed packets
- Introduce unsafe synthesis behavior

Security issues must be reported privately as described in SECURITY.md.

============================================================
## 8. Licensing
============================================================

All contributions to the Specification Plane are licensed under Apache 2.0.

Engine Plane contributions are not accepted.

============================================================
## 9. Summary
============================================================

This contribution guide ensures that all changes to REID v9.3 maintain
architectural integrity, temporal stability, and synthesis safety.

End of CONTRIBUTING.md
