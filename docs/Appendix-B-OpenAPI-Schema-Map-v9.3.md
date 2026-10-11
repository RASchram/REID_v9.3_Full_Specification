# Appendix B — OpenAPI 3.1 Schema Map (v9.3)

This appendix defines the authoritative OpenAPI 3.1 schema references for
SIL‑v9.3, AAG‑v9.3, ATS‑v9.3, and Binding Chain payloads. These definitions
ensure external API consumers encounter zero ambiguity when validating REID
v9.3 wire formats.

## B.1 SIL‑v9.3 Schema

SILv93:
  type: object
  required:
    - sil_state
    - sil_lock_hash
    - sil_version
    - gf_code
    - timestamp_utc
  properties:
    sil_state:
      type: string
      enum: [LOCKED, QUARANTINE, FAIL]
    sil_lock_hash:
      type: string
    sil_version:
      type: integer
      example: 93
    gf_code:
      type: integer
    timestamp_utc:
      type: integer
      format: int64

## B.2 AAG‑v9.3 Schema

AAGv93:
  type: object
  required:
    - aag_status
    - aag_directive
    - aag_version
    - gf_code
    - timestamp_utc
  properties:
    aag_status:
      type: string
      enum: [PASS, HOLD, REANCHOR]
    aag_directive:
      type: string
    aag_version:
      type: integer
      example: 93
    gf_code:
      type: integer
    timestamp_utc:
      type: integer
      format: int64

## B.3 ATS‑v9.3 Schema

ATSv93:
  type: object
  required:
    - epoch_id
    - epoch_sequence
    - timestamp_utc
    - td_score
    - tc_score
    - xdd_score
    - edd_score
    - model_id
    - gf_code
    - emission_hash
    - sil_state
    - sil_lock_hash
  properties:
    epoch_id:
      type: string
    epoch_sequence:
      type: integer
      format: int64
    timestamp_utc:
      type: integer
      format: int64
    td_score:
      type: number
    tc_score:
      type: number
    xdd_score:
      type: number
    edd_score:
      type: number
    model_id:
      type: string
    gf_code:
      type: integer
    emission_hash:
      type: string
    sil_state:
      type: string
      enum: [LOCKED, QUARANTINE]
    sil_lock_hash:
      type: string

## B.4 Binding Chain Schema

BindingChain:
  type: object
  required:
    - layer_id
    - epoch_id
    - drift_score
    - coherence_score
    - gf_code
  properties:
    layer_id:
      type: string
    epoch_id:
      type: string
    drift_score:
      type: number
    coherence_score:
      type: number
    gf_code:
      type: integer
