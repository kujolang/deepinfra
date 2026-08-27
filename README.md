# Kujo DeepInfra Provider

[![Version](https://img.shields.io/badge/version-0.1.1-black)](https://github.com/kujolang/deepinfra/releases/tag/v0.1.1)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)
[![built with Kujo](https://img.shields.io/badge/built%20with-Kujo-white.svg)](https://github.com/kujolang/kujo)

DeepInfra OpenAI-compatible chat plus native model inference for Kujo.

## Install

```bash
kujo run /path/to/kennel/kennel.kujo --interpreter -- add github:kujolang/deepinfra@v0.1.1 --alias deepinfra
kujo run /path/to/kennel/kennel.kujo --interpreter -- install
export DEEPINFRA_TOKEN=your-token
```

## 30-second quick start

```kujo
from deepinfra import create_client, client_chat

client := create_client({})
request := {
    "model": "deepseek-ai/DeepSeek-V3",
    "messages": [
        {
            "role": "user",
            "content": "Hello from Kujo!"
        }
    ]
}

result := client_chat(client, request)

print(result["data"]["choices"][0]["message"]["content"])
```

## Native API

The native layer preserves compatible chat, tools, reasoning, structured output, model listing, and native `/inference/{model}` responses for non-chat tasks.

## AI SDK integration

`deepinfra_provider({"model": "deepseek-ai/DeepSeek-V3"})` supplies normalized chat and streaming semantics. Use the native client for image, speech, reranking, and other model tasks.

## Authentication and security

Set `DEEPINFRA_TOKEN`. Remote endpoints require HTTPS; credentials are redacted and never committed to fixtures.

## Testing and documentation

```bash
bash scripts/release_quality_gate.sh
bash scripts/verify_installed_package.sh
```

The default gate is deterministic and offline. See [docs/](docs/) for implementation and Contract v1 evidence.
