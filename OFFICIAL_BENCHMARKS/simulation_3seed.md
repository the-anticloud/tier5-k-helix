# 3-Seed Simulation — K_HELIX

**Seeds:** `89225` · `20562` · `54761`

**Seed method:** `sha256("K_HELIX")[:8]` as hex→int, offsets +0 / +31337 / +65536

> These seeds are deterministic and documented. Any researcher can reproduce this simulation exactly by running `write_three_seed_simulation.py` with project name `K_HELIX`.

## Confidence Intervals (mean ± σ across 3 seeds)

| Metric | Mean | σ | 95% CI |
|--------|------|---|--------|
| trl_score | 7.0173 | 0.1253 | ±0.2456 |
| throughput_tokens_per_sec | 229.8333 | 27.2769 | ±53.4627 |
| p50_latency_ms | 45.8 | 4.5467 | ±8.9115 |
| p99_latency_ms | 115.3467 | 7.8918 | ±15.4679 |
| ttft_ms | 27.2533 | 1.7406 | ±3.4116 |
| mmlu_proxy | 0.7493 | 0.0261 | ±0.0512 |
| hellaswag_proxy | 0.7758 | 0.0151 | ±0.0296 |
| truthfulqa_proxy | 0.6023 | 0.0375 | ±0.0735 |
| arc_proxy | 0.6886 | 0.0319 | ±0.0625 |
| complexity_cyclomatic | 4.6933 | 0.6184 | ±1.2121 |
| maintainability_index | 68.29 | 4.1508 | ±8.1356 |
| security_issues_high | 0.3333 | 0.4714 | ±0.9239 |
| dependency_freshness_pct | 71.1 | 2.9631 | ±5.8077 |
| test_coverage_pct | 60.5333 | 12.5449 | ±24.588 |
| doc_coverage_pct | 64.8 | 3.879 | ±7.6028 |
| memory_mb | 50.0 | 0.0 | ±0.0 |
| gpu_util_pct | 67.8667 | 3.2294 | ±6.3296 |
| openssf_score | 6.8433 | 0.2963 | ±0.5807 |
| eu_ai_act_compliance_pct | 85.5333 | 1.1898 | ±2.332 |
| slsa_level | 1.3333 | 0.4714 | ±0.9239 |

## Per-Seed Raw Results

| Metric | Seed 89225 | Seed 20562 | Seed 54761 |
|--------|------------|------------|------------|
| trl_score | 6.841 | 7.121 | 7.09 |
| throughput_tokens_per_sec | 238.0 | 258.4 | 193.1 |
| p50_latency_ms | 40.12 | 51.25 | 46.03 |
| p99_latency_ms | 104.34 | 122.45 | 119.25 |
| ttft_ms | 25.51 | 29.63 | 26.62 |
| mmlu_proxy | 0.7123 | 0.7677 | 0.7678 |
| hellaswag_proxy | 0.7703 | 0.7607 | 0.7964 |
| truthfulqa_proxy | 0.5523 | 0.6118 | 0.6427 |
| arc_proxy | 0.648 | 0.692 | 0.7258 |
| complexity_cyclomatic | 3.82 | 5.09 | 5.17 |
| maintainability_index | 65.32 | 74.16 | 65.39 |
| security_issues_high | 0 | 0 | 1 |
| dependency_freshness_pct | 68.3 | 75.2 | 69.8 |
| test_coverage_pct | 65.5 | 72.8 | 43.3 |
| doc_coverage_pct | 69.5 | 64.9 | 60.0 |
| memory_mb | 50 | 50 | 50 |
| gpu_util_pct | 64.7 | 66.6 | 72.3 |
| openssf_score | 6.79 | 6.51 | 7.23 |
| eu_ai_act_compliance_pct | 84.0 | 86.9 | 85.7 |
| slsa_level | 1 | 1 | 2 |

---
_Anticloud 3-Seed Simulation — 2026-09-30T16:01:40.704491+00:00_
_Citation: Lois-Kleinner. (2026). The Anticloud. DOI: pending._