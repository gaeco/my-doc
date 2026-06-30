# Hello

```
wcsadmin@scp-wcsdgpu1:/data/wheels/train_pack_wheel$ pip install --no-index --find-links=/data/wheels/train_pack_wheel/wheels -r requirements-train.txt
Looking in links: /data/wheels/train_pack_wheel/wheels
Processing ./wheels/transformers-5.12.1-py3-none-any.whl (from -r requirements-train.txt (line 1))
Processing ./wheels/trl-1.7.0-py3-none-any.whl (from -r requirements-train.txt (line 2))
Processing ./wheels/peft-0.19.1-py3-none-any.whl (from -r requirements-train.txt (line 3))
Processing ./wheels/accelerate-1.14.0-py3-none-any.whl (from -r requirements-train.txt (line 4))
Processing ./wheels/datasets-5.0.0-py3-none-any.whl (from -r requirements-train.txt (line 5))
Processing ./wheels/qwen_vl_utils-0.0.14-py3-none-any.whl (from -r requirements-train.txt (line 6))
Processing ./wheels/huggingface_hub-1.21.0-py3-none-any.whl (from transformers->-r requirements-train.txt (line 1))
INFO: pip is looking at multiple versions of transformers to determine which version is compatible with other requirements. This could take a while.
ERROR: Could not find a version that satisfies the requirement numpy>=1.17 (from transformers) (from versions: none)
ERROR: No matching distribution found for numpy>=1.17


```
