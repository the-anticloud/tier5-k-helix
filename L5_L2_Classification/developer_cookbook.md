# Developer Cookbook — K_HELIX
**Stack:** Python 3.11, PyTorch 2.10+, Warp (NVIDIA physics), PAX 27B, AIOSS_FORMAT
**Domain:** Helix: neural physics engine for embodied AI simulation in Anticloud

## Physics simulation
```python
from k_helix import HelixSimulator

sim = HelixSimulator(
    scene_config="./anticloud_robot_scene.json",
    pax_model="./pax-27b-q4.gguf",
    aioss_chain="./helix.aioss"
)

# Run 1000 parallel episodes
results = sim.run_batch(
    task="pick and place object",
    n_episodes=1000,
    randomize=True
)
print(f"Success rate: {results.success_rate:.2%}")
print(f"Chain: {results.chain_hash}")
```

## Language-configured scene
```python
scene = sim.configure_from_language(
    "Simulate a robot arm on a 30-degree inclined surface picking up a 500g sphere",
    pax_model="./pax-27b-q4.gguf"
)
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
