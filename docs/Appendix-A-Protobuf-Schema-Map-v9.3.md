# Appendix A — Protobuf Schema Map (v9.3)

This appendix defines the authoritative field‑ID mappings for all REID v9.3
wire‑format payloads, including SIL‑v9.3, AAG‑v9.3, ATS‑v9.3, and the Binding
Chain primitives. These mappings ensure external implementations encounter zero
ambiguity when parsing REID packets.

## A.1 SIL‑v9.3 Field IDs

message SILv93 {
  uint32 sil_state            = 1;   // LOCKED, QUARANTINE, FAIL
  string sil_lock_hash        = 2;   // SHA‑256 lock seal
  uint32 sil_version          = 3;   // v9.3
  uint32 gf_code              = 4;   // GF‑CLASS‑1/2
  uint64 timestamp_utc        = 5;   // authoritative timestamp
}

## A.2 AAG‑v9.3 Field IDs

message AAGv93 {
  uint32 aag_status           = 1;   // HOLD, PASS, REANCHOR
  string aag_directive        = 2;   // governance directive
  uint32 aag_version          = 3;   // v9.3
  uint32 gf_code              = 4;   // GF‑CLASS‑1/2
  uint64 timestamp_utc        = 5;
}

## A.3 ATS‑v9.3 Field IDs

message ATSv93 {
  string epoch_id             = 1;
  uint64 epoch_sequence       = 2;
  uint64 timestamp_utc        = 3;
  float td_score              = 4;
  float tc_score              = 5;
  float xdd_score             = 6;
  float edd_score             = 7;
  string model_id             = 8;
  uint32 gf_code              = 9;
  string emission_hash        = 10;
  string sil_state            = 11;  // LOCKED, QUARANTINE
  string sil_lock_hash        = 12;
}

## A.4 Binding Chain Field IDs

message BindingChain {
  string layer_id             = 1;   // L1, IC, L2, ..., UC, CL
  string epoch_id             = 2;
  float drift_score           = 3;
  float coherence_score       = 4;
  uint32 gf_code              = 5;
}
