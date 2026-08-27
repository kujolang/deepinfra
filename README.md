# Kujo DeepInfra Provider

Native DeepInfra OpenAI-compatible chat client with DeepInfra reasoning, tools, vision, and an AI SDK adapter.

```bash
kujo package-add github:kujolang/deepinfra@v0.1.0
export DEEPINFRA_TOKEN=your-token
```

```kujo
from deepinfra import create_client, client_chat
c := create_client({})
r := client_chat(c, {"model":"deepseek-ai/DeepSeek-V3","messages":[{"role":"user","content":"Hello"}],"reasoning_effort":"high"})
```

Native use preserves DeepInfra response fields, reasoning controls, tools, and usage metadata. `deepinfra_provider()` supplies normalized AI SDK chat and streaming semantics. Tests are offline and credential-free.
