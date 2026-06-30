# Hello

```
wcsadmin@scp-wcsdgpu1:/data/wheels/train_pack_wheel$ ls
requirements-train.txt  wheels
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
wcsadmin@scp-wcsdgpu1:/data/wheels/train_pack_wheel$ ls wheels/
accelerate-1.14.0-py3-none-any.whl
aiohappyeyeballs-2.6.2-py3-none-any.whl
aiohttp-3.14.1-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
aiosignal-1.4.0-py3-none-any.whl
annotated_doc-0.0.4-py3-none-any.whl
anyio-4.14.1-py3-none-any.whl
attrs-26.1.0-py3-none-any.whl
av-17.1.0-cp311-abi3-manylinux_2_28_x86_64.whl
certifi-2026.6.17-py3-none-any.whl
charset_normalizer-3.4.7-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
click-8.4.2-py3-none-any.whl
cuda_bindings-13.3.1-cp312-cp312-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl
cuda_pathfinder-1.5.6-py3-none-any.whl
cuda_toolkit-13.0.2-py2.py3-none-any.whl
datasets-5.0.0-py3-none-any.whl
dill-0.4.1-py3-none-any.whl
filelock-3.29.4-py3-none-any.whl
frozenlist-1.8.0-cp312-cp312-manylinux1_x86_64.manylinux_2_28_x86_64.manylinux_2_5_x86_64.whl
fsspec-2026.4.0-py3-none-any.whl
h11-0.16.0-py3-none-any.whl
hf_xet-1.5.1-cp37-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl
httpcore-1.0.9-py3-none-any.whl
httpx-0.28.1-py3-none-any.whl
huggingface_hub-1.21.0-py3-none-any.whl
idna-3.18-py3-none-any.whl
jinja2-3.1.6-py3-none-any.whl
markdown_it_py-4.2.0-py3-none-any.whl
markupsafe-3.0.3-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
mdurl-0.1.2-py3-none-any.whl
mpmath-1.3.0-py3-none-any.whl
multidict-6.7.1-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
multiprocess-0.70.19-py312-none-any.whl
networkx-3.6.1-py3-none-any.whl
numpy-2.5.0-cp312-cp312-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl
nvidia_cublas-13.1.1.3-py3-none-manylinux_2_27_x86_64.whl
nvidia_cuda_cupti-13.0.85-py3-none-manylinux_2_25_x86_64.whl
nvidia_cuda_nvrtc-13.0.88-py3-none-manylinux2010_x86_64.manylinux_2_12_x86_64.whl
nvidia_cuda_runtime-13.0.96-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl
nvidia_cudnn_cu13-9.20.0.48-py3-none-manylinux_2_27_x86_64.whl
nvidia_cufft-12.0.0.61-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl
nvidia_cufile-1.15.1.6-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl
nvidia_curand-10.4.0.35-py3-none-manylinux_2_27_x86_64.whl
nvidia_cusolver-12.0.4.66-py3-none-manylinux_2_27_x86_64.whl
nvidia_cusparse-12.6.3.3-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl
nvidia_cusparselt_cu13-0.8.1-py3-none-manylinux2014_x86_64.whl
nvidia_nccl_cu13-2.29.7-py3-none-manylinux_2_18_x86_64.whl
nvidia_nvjitlink-13.0.88-py3-none-manylinux2010_x86_64.manylinux_2_12_x86_64.whl
nvidia_nvshmem_cu13-3.4.5-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl
nvidia_nvtx-13.0.85-py3-none-manylinux1_x86_64.manylinux_2_5_x86_64.whl
packaging-26.2-py3-none-any.whl
pandas-3.0.3-cp312-cp312-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl
peft-0.19.1-py3-none-any.whl
pillow-12.2.0-cp312-cp312-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl
propcache-0.5.2-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
psutil-7.2.2-cp36-abi3-manylinux2010_x86_64.manylinux_2_12_x86_64.manylinux_2_28_x86_64.whl
pyarrow-24.0.0-cp312-cp312-manylinux_2_28_x86_64.whl
pygments-2.20.0-py3-none-any.whl
python_dateutil-2.9.0.post0-py2.py3-none-any.whl
pyyaml-6.0.3-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
qwen_vl_utils-0.0.14-py3-none-any.whl
regex-2026.6.28-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
requests-2.34.2-py3-none-any.whl
rich-15.0.0-py3-none-any.whl
safetensors-0.8.0-cp310-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl
setuptools-81.0.0-py3-none-any.whl
shellingham-1.5.4-py2.py3-none-any.whl
six-1.17.0-py2.py3-none-any.whl
sympy-1.14.0-py3-none-any.whl
tokenizers-0.22.2-cp39-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl
torch-2.12.1-cp312-cp312-manylinux_2_28_x86_64.whl
tqdm-4.68.3-py3-none-any.whl
transformers-5.12.1-py3-none-any.whl
triton-3.7.1-cp312-cp312-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl
trl-1.7.0-py3-none-any.whl
typer-0.25.1-py3-none-any.whl
typing_extensions-4.15.0-py3-none-any.whl
urllib3-2.7.0-py3-none-any.whl
xxhash-3.8.0-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
yarl-1.24.2-cp312-cp312-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl
wcsadmin@scp-wcsdgpu1:/data/wheels/train_pack_wheel$



```
