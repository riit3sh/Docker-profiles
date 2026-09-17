FROM vllm/vllm-openai:v0.9.2

# Pin transformers to 5.16.1 which adds native qwen3_5 architecture support
# v0.9.2 ships with an older transformers that doesn't know qwen3_5
RUN pip install --no-cache-dir "transformers==5.16.1"

# Verify versions in the build log so we always know what's inside
RUN python3 -c "import vllm, transformers; print(f'vLLM: {vllm.__version__} | Transformers: {transformers.__version__}')"

# Keep the default vLLM entrypoint
ENTRYPOINT ["python3", "-m", "vllm.entrypoints.openai.api_server"]
