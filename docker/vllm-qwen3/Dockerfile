FROM vllm/vllm-openai:v0.6.3

# Install latest transformers to support qwen3_5 architectures
RUN pip install --no-cache-dir -U "transformers>=5.0.0"

# Verify the versions in the build log
RUN python3 -c "import vllm, transformers; print(f'vLLM: {vllm.__version__} | Transformers: {transformers.__version__}')"

# Keep the default vLLM entrypoint
ENTRYPOINT ["python3", "-m", "vllm.entrypoints.openai.api_server"]
