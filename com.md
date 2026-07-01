## Hello
```
(base) wcsadmin@scp-wcsdgpu1:~/vllm$ sudo docker run -d --name vllm \
        --gpus all \
        --ipc=host \
        -v /data/ai-models:/models \
        -p 8000:8000 \
        -e HF_HUB_OFFLINE=1 \
        -e TRANSFORMERS_OFFLINE=1 \
        vllm/vllm-openai:v0.23.0 \
        --model /models/Qwen2.5-VL-7B-Instruct \
        --served-model-name qwen2.5-vl \
        --gpu-memory-utilization 0.22 \
        --trust-remote-code
3fae88a27e653fac4ae4186801f63d0817c1217d5f6845e1504ef77670145109
(base) wcsadmin@scp-wcsdgpu1:~/vllm$ sudo docker logs -f 3fae88a27
WARNING 07-01 04:23:28 [argparse_utils.py:257] With `vllm serve`, you should provide the model as a positional argument or in a config file instead of via the `--model` option. The `--model` option will be removed in a future version.
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:339]
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:339]        █     █     █▄   ▄█
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:339]  ▄▄ ▄█ █     █     █ ▀▄▀ █  version 0.23.0
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:339]   █▄█▀ █     █     █     █  model   /models/Qwen2.5-VL-7B-Instruct
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:339]    ▀▀  ▀▀▀▀▀ ▀▀▀▀▀ ▀     ▀
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:339]
(APIServer pid=1) INFO 07-01 04:23:28 [api_utils.py:273] non-default args: {'model_tag': '/models/Qwen2.5-VL-7B-Instruct', 'model': '/models/Qwen2.5-VL-7B-Instruct', 'trust_remote_code': True, 'served_model_name': ['qwen2.5-vl'], 'gpu_memory_utilization': 0.22}
(APIServer pid=1) WARNING 07-01 04:23:28 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_BUILD_COMMIT
(APIServer pid=1) WARNING 07-01 04:23:28 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_BUILD_PIPELINE
(APIServer pid=1) WARNING 07-01 04:23:28 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_BUILD_URL
(APIServer pid=1) WARNING 07-01 04:23:28 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_IMAGE_TAG
(APIServer pid=1) INFO 07-01 04:23:39 [model.py:611] Resolved architecture: Qwen2_5_VLForConditionalGeneration
(APIServer pid=1) INFO 07-01 04:23:39 [model.py:1745] Using max model len 128000
(APIServer pid=1) INFO 07-01 04:23:39 [vllm.py:999] Asynchronous scheduling is enabled.
(APIServer pid=1) INFO 07-01 04:23:39 [kernel.py:270] Final IR op priority after setting platform defaults: IrOpPriorityConfig(rms_norm=['native'], fused_add_rms_norm=['native'])
(APIServer pid=1) [transformers] The `use_fast` parameter is deprecated and will be removed in a future version. Use `backend="torchvision"` instead of `use_fast=True`, or `backend="pil"` instead of `use_fast=False`.
(EngineCore pid=129) INFO 07-01 04:23:50 [core.py:113] Initializing a V1 LLM engine (v0.23.0) with config: model='/models/Qwen2.5-VL-7B-Instruct', speculative_config=None, tokenizer='/models/Qwen2.5-VL-7B-Instruct', skip_tokenizer_init=False, tokenizer_mode=auto, revision=None, tokenizer_revision=None, trust_remote_code=True, dtype=torch.bfloat16, max_seq_len=128000, download_dir=None, load_format=auto, tensor_parallel_size=1, pipeline_parallel_size=1, data_parallel_size=1, decode_context_parallel_size=1, dcp_comm_backend=ag_rs, disable_custom_all_reduce=False, quantization=None, quantization_config=None, enforce_eager=False, enable_return_routed_experts=False, kv_cache_dtype=auto, device_config=cuda, structured_outputs_config=StructuredOutputsConfig(backend='auto', disable_any_whitespace=False, disable_additional_properties=False, reasoning_parser='', reasoning_parser_plugin='', enable_in_reasoning=False), observability_config=ObservabilityConfig(show_hidden_metrics_for_version=None, otlp_traces_endpoint=None, collect_detailed_traces=None, kv_cache_metrics=False, kv_cache_metrics_sample=0.01, cudagraph_metrics=False, enable_layerwise_nvtx_tracing=False, enable_mfu_metrics=False, enable_mm_processor_stats=False, enable_logging_iteration_details=False), seed=0, served_model_name=qwen2.5-vl, enable_prefix_caching=True, enable_chunked_prefill=True, pooler_config=None, compilation_config={'mode': <CompilationMode.VLLM_COMPILE: 3>, 'debug_dump_path': None, 'cache_dir': '', 'compile_cache_save_format': 'binary', 'backend': 'inductor', 'custom_ops': ['none'], 'ir_enable_torch_wrap': True, 'splitting_ops': ['vllm::unified_attention_with_output', 'vllm::unified_mla_attention_with_output', 'vllm::mamba_mixer2', 'vllm::mamba_mixer', 'vllm::short_conv', 'vllm::linear_attention', 'vllm::plamo2_mamba_mixer', 'vllm::qwen_gdn_attention_core', 'vllm::gdn_attention_core_xpu', 'vllm::olmo_hybrid_gdn_full_forward', 'vllm::kda_attention', 'vllm::sparse_attn_indexer', 'vllm::rocm_aiter_sparse_attn_indexer', 'vllm::deepseek_v4_attention', 'vllm::unified_kv_cache_update', 'vllm::unified_mla_kv_cache_update'], 'compile_mm_encoder': False, 'cudagraph_mm_encoder': False, 'encoder_cudagraph_token_budgets': [], 'encoder_cudagraph_max_vision_items_per_batch': 0, 'encoder_cudagraph_max_frames_per_batch': None, 'compile_sizes': [], 'compile_ranges_endpoints': [2048], 'inductor_compile_config': {'enable_auto_functionalized_v2': False, 'size_asserts': False, 'alignment_asserts': False, 'scalar_asserts': False, 'combo_kernels': True, 'benchmark_combo_kernel': True}, 'inductor_passes': {}, 'cudagraph_mode': <CUDAGraphMode.FULL_AND_PIECEWISE: (2, 1)>, 'cudagraph_num_of_warmups': 1, 'cudagraph_capture_sizes': [1, 2, 4, 8, 16, 24, 32, 40, 48, 56, 64, 72, 80, 88, 96, 104, 112, 120, 128, 136, 144, 152, 160, 168, 176, 184, 192, 200, 208, 216, 224, 232, 240, 248, 256, 272, 288, 304, 320, 336, 352, 368, 384, 400, 416, 432, 448, 464, 480, 496, 512], 'cudagraph_copy_inputs': False, 'cudagraph_specialize_lora': True, 'use_inductor_graph_partition': False, 'pass_config': {'fuse_norm_quant': False, 'fuse_act_quant': False, 'fuse_attn_quant': False, 'enable_sp': False, 'fuse_gemm_comms': False, 'fuse_allreduce_rms': False, 'fuse_rope_kvcache_cat_mla': False, 'fuse_act_padding': False}, 'max_cudagraph_capture_size': 512, 'dynamic_shapes_config': {'type': <DynamicShapesType.BACKED: 'backed'>, 'evaluate_guards': False, 'assume_32_bit_indexing': False}, 'local_cache_dir': None, 'fast_moe_cold_start': False, 'static_all_moe_layers': []}, kernel_config=KernelConfig(ir_op_priority=IrOpPriorityConfig(rms_norm=['native'], fused_add_rms_norm=['native']), enable_flashinfer_autotune=True, moe_backend='auto', linear_backend='auto')
(EngineCore pid=129) INFO 07-01 04:23:52 [parallel_state.py:1568] world_size=1 rank=0 local_rank=0 distributed_init_method=tcp://172.17.0.2:50037 backend=nccl
[W701 04:23:52.466230535 socket.cpp:764] [c10d] The client socket cannot be initialized to connect to [::ffff:172.17.0.2]:50037 (errno: 97 - Address family not supported by protocol).
(EngineCore pid=129) INFO 07-01 04:23:52 [parallel_state.py:1903] rank 0 in world size 1 is assigned as DP rank 0, PP rank 0, PCP rank 0, TP rank 0, EP rank N/A, EPLB rank N/A
(EngineCore pid=129) INFO 07-01 04:23:52 [topk_topp_sampler.py:55] Using FlashInfer for top-p & top-k sampling.
(EngineCore pid=129) [transformers] The `use_fast` parameter is deprecated and will be removed in a future version. Use `backend="torchvision"` instead of `use_fast=True`, or `backend="pil"` instead of `use_fast=False`.
(EngineCore pid=129) INFO 07-01 04:23:55 [gpu_model_runner.py:5092] Starting to load model /models/Qwen2.5-VL-7B-Instruct...
(EngineCore pid=129) INFO 07-01 04:23:56 [cuda.py:433] Using backend AttentionBackendEnum.FLASH_ATTN for vit attention
(EngineCore pid=129) INFO 07-01 04:23:56 [mm_encoder_attention.py:372] Using AttentionBackendEnum.FLASH_ATTN for MMEncoderAttention.
(EngineCore pid=129) INFO 07-01 04:23:56 [vllm.py:999] Asynchronous scheduling is enabled.
(EngineCore pid=129) INFO 07-01 04:23:56 [kernel.py:270] Final IR op priority after setting platform defaults: IrOpPriorityConfig(rms_norm=['native'], fused_add_rms_norm=['native'])
(EngineCore pid=129) INFO 07-01 04:23:56 [cuda.py:378] Using FLASH_ATTN attention backend out of potential backends: ['FLASH_ATTN', 'FLASHINFER', 'TRITON_ATTN', 'FLEX_ATTENTION'].
(EngineCore pid=129) INFO 07-01 04:23:56 [flash_attn.py:636] Using FlashAttention version 2
(EngineCore pid=129) INFO 07-01 04:23:56 [weight_utils.py:922] Filesystem type for checkpoints: EXT4. Checkpoint size: 15.45 GiB. Available RAM: 218.63 GiB.
(EngineCore pid=129) INFO 07-01 04:23:56 [weight_utils.py:945] Auto-prefetch is disabled because the filesystem (EXT4) is not a recognized network FS (NFS/Lustre). If you want to force prefetching, start vLLM with --safetensors-load-strategy=prefetch.
Loading safetensors checkpoint shards:   0% Completed | 0/5 [00:00<?, ?it/s]
Loading safetensors checkpoint shards:  20% Completed | 1/5 [00:00<00:02,  1.75it/s]
Loading safetensors checkpoint shards:  40% Completed | 2/5 [00:01<00:01,  1.71it/s]
Loading safetensors checkpoint shards:  60% Completed | 3/5 [00:01<00:01,  1.70it/s]
Loading safetensors checkpoint shards:  80% Completed | 4/5 [00:02<00:00,  1.70it/s]
Loading safetensors checkpoint shards: 100% Completed | 5/5 [00:02<00:00,  2.23it/s]
Loading safetensors checkpoint shards: 100% Completed | 5/5 [00:02<00:00,  1.96it/s]
(EngineCore pid=129)
(EngineCore pid=129) INFO 07-01 04:23:58 [default_loader.py:397] Loading weights took 2.56 seconds
(EngineCore pid=129) INFO 07-01 04:23:59 [gpu_model_runner.py:5187] Model loading took 15.67 GiB memory and 2.938506 seconds
(EngineCore pid=129) INFO 07-01 04:23:59 [gpu_model_runner.py:6200] Encoder cache will be initialized with a budget of 114688 tokens, and profiled with 1 video items of the maximum feature size.
(EngineCore pid=129) INFO 07-01 04:24:18 [backends.py:1089] Using cache directory: /root/.cache/vllm/torch_compile_cache/41b7c9b698/rank_0_0/backbone for vLLM's torch.compile
(EngineCore pid=129) INFO 07-01 04:24:18 [backends.py:1148] Dynamo bytecode transform time: 4.70 s
(EngineCore pid=129) INFO 07-01 04:24:21 [backends.py:378] Cache the graph of compile range (1, 2048) for later use
(EngineCore pid=129) INFO 07-01 04:24:26 [backends.py:393] Compiling a graph for compile range (1, 2048) takes 8.43 s
(EngineCore pid=129) INFO 07-01 04:24:29 [decorators.py:708] saved AOT compiled function to /root/.cache/vllm/torch_compile_cache/torch_aot_compile/4ce3b7ad6f879089348ce1064a00971d9d3e08834e8395fc2fb00c4a9b00f836/rank_0_0/model
(EngineCore pid=129) INFO 07-01 04:24:29 [monitor.py:53] torch.compile took 16.07 s in total
(EngineCore pid=129) INFO 07-01 04:24:29 [monitor.py:81] Initial profiling/warmup run took 0.45 s
(EngineCore pid=129) INFO 07-01 04:24:36 [gpu_model_runner.py:6412] Profiling CUDA graph memory: PIECEWISE=51 (largest=512), FULL=35 (largest=256)
(EngineCore pid=129) INFO 07-01 04:24:37 [gpu_model_runner.py:6517] Estimated CUDA graph memory: 0.53 GiB total
(EngineCore pid=129) INFO 07-01 04:24:37 [gpu_worker.py:480] Available KV cache memory: -14.28 GiB
(EngineCore pid=129) INFO 07-01 04:24:37 [gpu_worker.py:495] CUDA graph memory profiling is enabled (default since v0.21.0). The current --gpu-memory-utilization=0.2200 is equivalent to --gpu-memory-utilization=0.2133 without CUDA graph memory profiling. To maintain the same effective KV cache size as before, increase --gpu-memory-utilization to 0.2267. To disable, set VLLM_MEMORY_PROFILER_ESTIMATE_CUDAGRAPHS=0.
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195] EngineCore failed to start.
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195] Traceback (most recent call last):
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 1164, in run_engine_core
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     engine_core = EngineCoreProc(*args, engine_index=dp_rank, **kwargs)
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/tracing/otel.py", line 178, in sync_wrapper
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     return func(*args, **kwargs)
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 930, in __init__
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     super().__init__(
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 132, in __init__
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     kv_cache_config = self._initialize_kv_caches(vllm_config)
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/tracing/otel.py", line 178, in sync_wrapper
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     return func(*args, **kwargs)
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 268, in _initialize_kv_caches
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     kv_cache_configs = get_kv_cache_configs(
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]                        ^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/core/kv_cache_utils.py", line 2052, in get_kv_cache_configs
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     _check_enough_kv_cache_memory(
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/core/kv_cache_utils.py", line 720, in _check_enough_kv_cache_memory
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195]     raise ValueError(
(EngineCore pid=129) ERROR 07-01 04:24:37 [core.py:1195] ValueError: No available memory for the cache blocks. Try increasing `gpu_memory_utilization` when initializing the engine (this flag also controls CPU memory reservation on the CPU backend, despite its name). See https://docs.vllm.ai/en/latest/configuration/conserving_memory/ for more details.
(EngineCore pid=129) Process EngineCore:
(EngineCore pid=129) Traceback (most recent call last):
(EngineCore pid=129)   File "/usr/lib/python3.12/multiprocessing/process.py", line 314, in _bootstrap
(EngineCore pid=129)     self.run()
(EngineCore pid=129)   File "/usr/lib/python3.12/multiprocessing/process.py", line 108, in run
(EngineCore pid=129)     self._target(*self._args, **self._kwargs)
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 1199, in run_engine_core
(EngineCore pid=129)     raise e
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 1164, in run_engine_core
(EngineCore pid=129)     engine_core = EngineCoreProc(*args, engine_index=dp_rank, **kwargs)
(EngineCore pid=129)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/tracing/otel.py", line 178, in sync_wrapper
(EngineCore pid=129)     return func(*args, **kwargs)
(EngineCore pid=129)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 930, in __init__
(EngineCore pid=129)     super().__init__(
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 132, in __init__
(EngineCore pid=129)     kv_cache_config = self._initialize_kv_caches(vllm_config)
(EngineCore pid=129)                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/tracing/otel.py", line 178, in sync_wrapper
(EngineCore pid=129)     return func(*args, **kwargs)
(EngineCore pid=129)            ^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core.py", line 268, in _initialize_kv_caches
(EngineCore pid=129)     kv_cache_configs = get_kv_cache_configs(
(EngineCore pid=129)                        ^^^^^^^^^^^^^^^^^^^^^
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/core/kv_cache_utils.py", line 2052, in get_kv_cache_configs
(EngineCore pid=129)     _check_enough_kv_cache_memory(
(EngineCore pid=129)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/core/kv_cache_utils.py", line 720, in _check_enough_kv_cache_memory
(EngineCore pid=129)     raise ValueError(
(EngineCore pid=129) ValueError: No available memory for the cache blocks. Try increasing `gpu_memory_utilization` when initializing the engine (this flag also controls CPU memory reservation on the CPU backend, despite its name). See https://docs.vllm.ai/en/latest/configuration/conserving_memory/ for more details.
[rank0]:[W701 04:24:38.847392355 ProcessGroupNCCL.cpp:1575] Warning: WARNING: destroy_process_group() was not called before program exit, which can leak resources. For more info, please see https://pytorch.org/docs/stable/distributed.html#shutdown (function operator())
(APIServer pid=1) Traceback (most recent call last):
(APIServer pid=1)   File "/usr/local/bin/vllm", line 10, in <module>
(APIServer pid=1)     sys.exit(main())
(APIServer pid=1)              ^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/cli/main.py", line 95, in main
(APIServer pid=1)     args.dispatch_function(args)
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/cli/serve.py", line 148, in cmd
(APIServer pid=1)     uvloop.run(run_server(args))
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/uvloop/__init__.py", line 96, in run
(APIServer pid=1)     return __asyncio.run(
(APIServer pid=1)            ^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/lib/python3.12/asyncio/runners.py", line 195, in run
(APIServer pid=1)     return runner.run(main)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/lib/python3.12/asyncio/runners.py", line 118, in run
(APIServer pid=1)     return self._loop.run_until_complete(task)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "uvloop/loop.pyx", line 1518, in uvloop.loop.Loop.run_until_complete
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/uvloop/__init__.py", line 48, in wrapper
(APIServer pid=1)     return await main
(APIServer pid=1)            ^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/openai/api_server.py", line 665, in run_server
(APIServer pid=1)     await run_server_worker(listen_address, sock, args, **uvicorn_kwargs)
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/openai/api_server.py", line 679, in run_server_worker
(APIServer pid=1)     async with build_async_engine_client(
(APIServer pid=1)                ^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/lib/python3.12/contextlib.py", line 210, in __aenter__
(APIServer pid=1)     return await anext(self.gen)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/openai/api_server.py", line 99, in build_async_engine_client
(APIServer pid=1)     async with build_async_engine_client_from_engine_args(
(APIServer pid=1)                ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/lib/python3.12/contextlib.py", line 210, in __aenter__
(APIServer pid=1)     return await anext(self.gen)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/openai/api_server.py", line 135, in build_async_engine_client_from_engine_args
(APIServer pid=1)     async_llm = AsyncLLM.from_vllm_config(
(APIServer pid=1)                 ^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/async_llm.py", line 217, in from_vllm_config
(APIServer pid=1)     return cls(
(APIServer pid=1)            ^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/async_llm.py", line 146, in __init__
(APIServer pid=1)     self.engine_core = EngineCoreClient.make_async_mp_client(
(APIServer pid=1)                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/tracing/otel.py", line 178, in sync_wrapper
(APIServer pid=1)     return func(*args, **kwargs)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 131, in make_async_mp_client
(APIServer pid=1)     return AsyncMPClient(*client_args)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/tracing/otel.py", line 178, in sync_wrapper
(APIServer pid=1)     return func(*args, **kwargs)
(APIServer pid=1)            ^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 948, in __init__
(APIServer pid=1)     super().__init__(
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/core_client.py", line 570, in __init__
(APIServer pid=1)     with launch_core_engines(
(APIServer pid=1)          ^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/lib/python3.12/contextlib.py", line 144, in __exit__
(APIServer pid=1)     next(self.gen)
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 1190, in launch_core_engines
(APIServer pid=1)     wait_for_engine_startup(
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/v1/engine/utils.py", line 1249, in wait_for_engine_startup
(APIServer pid=1)     raise RuntimeError(
(APIServer pid=1) RuntimeError: Engine core initialization failed. See root cause above. Failed core proc(s): {}
(base) wcsadmin@scp-wcsdgpu1:~/vllm$ nvidia-smi
Wed Jul  1 13:25:22 2026
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 570.195.03             Driver Version: 570.195.03     CUDA Version: 12.8     |
|-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA A100-SXM4-80GB          On  |   00000000:00:06.0 Off |                    0 |
| N/A   33C    P0             54W /  500W |       0MiB /  81920MiB |      0%      Default |
|                                         |                        |             Disabled |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI              PID   Type   Process name                        GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|  No running processes found                                                             |
+-----------------------------------------------------------------------------------------+
(base) wcsadmin@scp-wcsdgpu1:~/vllm$

```
