# Deploy Guide — K_HELIX
**Tier:** TIER_5_WORLD_NEURO_EMBODIED | **Stack:** Python 3.11, PyTorch 2.10+, Warp (NVIDIA physics), PAX 27B, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, NVIDIA Warp 0.x, PyTorch 2.10+, T4/A100 GPU (CUDA required for Warp).

## Environment
T4 GPU minimum for Warp physics simulation. 16GB VRAM for large-scale parallel sim.

## AIOSS Integration
```bash
aioss init --module K_HELIX --output ./k_helix.aioss
aioss append --chain ./k_helix.aioss --payload ./output.bin --module K_HELIX
aioss verify --chain ./k_helix.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="K_HELIX",
    aioss_chain="./K_HELIX.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./K_HELIX.aioss --verbose
python -m K_HELIX.tests.smoke
```
