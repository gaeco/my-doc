# Hello

```
sudo docker run -d --name vllm-coder-next \
        --gpus all \
        --ipc=host \
        -v /data/ai-models:/models \
        -p 8002:8000 \
        -e HF_HUB_OFFLINE=1 \
        -e TRANSFORMERS_OFFLINE=1 \
        vllm/vllm-openai:v0.23.0 \
        --model /models/Qwen3-Coder-Next \
        --served-model-name qwen3-coder-next \
        --trust-remote-code \
        --quantization awq_marlin \
        --dtype bfloat16 \
        --gpu-memory-utilization 0.64 \
        --kv-cache-dtype fp8 \
        --max-model-len 32768 \
        --max-num-seqs 8 \
        --enable-prefix-caching \
        --enable-auto-tool-choice \
        --tool-call-parser qwen3_coder

(base) wcsadmin@scp-wcsdgpu1:~/vllm$ sudo docker logs -f 4ccf8dc5099a
WARNING 06-30 23:14:18 [argparse_utils.py:257] With `vllm serve`, you should provide the model as a positional argument or in a config file instead of via the `--model` option. The `--model` option will be removed in a future version.
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:339]
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:339]        █     █     █▄   ▄█
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:339]  ▄▄ ▄█ █     █     █ ▀▄▀ █  version 0.23.0
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:339]   █▄█▀ █     █     █     █  model   /models/Qwen3-Coder-Next
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:339]    ▀▀  ▀▀▀▀▀ ▀▀▀▀▀ ▀     ▀
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:339]
(APIServer pid=1) INFO 06-30 23:14:18 [api_utils.py:273] non-default args: {'model_tag': '/models/Qwen3-Coder-Next', 'enable_auto_tool_choice': True, 'tool_call_parser': 'qwen3_coder', 'model': '/models/Qwen3-Coder-Next', 'trust_remote_code': True, 'dtype': 'bfloat16', 'max_model_len': 32768, 'quantization': 'awq_marlin', 'served_model_name': ['qwen3-coder-next'], 'gpu_memory_utilization': 0.64, 'kv_cache_dtype': 'fp8', 'enable_prefix_caching': True, 'max_num_seqs': 8}
(APIServer pid=1) WARNING 06-30 23:14:18 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_BUILD_COMMIT
(APIServer pid=1) WARNING 06-30 23:14:18 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_BUILD_PIPELINE
(APIServer pid=1) WARNING 06-30 23:14:18 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_BUILD_URL
(APIServer pid=1) WARNING 06-30 23:14:18 [envs.py:2088] Unknown vLLM environment variable detected: VLLM_IMAGE_TAG
(APIServer pid=1) INFO 06-30 23:14:29 [model.py:611] Resolved architecture: Qwen3NextForCausalLM
(APIServer pid=1) INFO 06-30 23:14:29 [model.py:1745] Using max model len 32768
(APIServer pid=1) INFO 06-30 23:14:29 [cache.py:269] Using fp8 data type to store kv cache. It reduces the GPU memory footprint and boosts the performance. Meanwhile, it may cause accuracy drop without a proper scaling factor
(APIServer pid=1) WARNING 06-30 23:14:29 [config.py:355] Mamba cache mode is set to 'align' for Qwen3NextForCausalLM by default when prefix caching is enabled
(APIServer pid=1) INFO 06-30 23:14:29 [config.py:375] Warning: Prefix caching in Mamba cache 'align' mode is currently enabled. Its support for Mamba layers is experimental. Please report any issues you may observe.
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
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/entrypoints/openai/api_server.py", line 123, in build_async_engine_client_from_engine_args
(APIServer pid=1)     vllm_config = engine_args.create_engine_config(usage_context=usage_context)
(APIServer pid=1)                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/vllm/engine/arg_utils.py", line 2229, in create_engine_config
(APIServer pid=1)     config = VllmConfig(
(APIServer pid=1)              ^^^^^^^^^^^
(APIServer pid=1)   File "/usr/local/lib/python3.12/dist-packages/pydantic/_internal/_dataclasses.py", line 121, in __init__
(APIServer pid=1)     s.__pydantic_validator__.validate_python(ArgsKwargs(args, kwargs), self_instance=s)
(APIServer pid=1) pydantic_core._pydantic_core.ValidationError: 1 validation error for VllmConfig
(APIServer pid=1)   Value error, Cannot find the config file for awq_marlin [type=value_error, input_value=ArgsKwargs((), {'model_co... 'shutdown_timeout': 0}), input_type=ArgsKwargs]
(APIServer pid=1)     For further information visit https://errors.pydantic.dev/2.13/v/value_error
```
