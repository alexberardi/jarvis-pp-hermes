# Hermes 3 Prompt Providers

Prompt providers for [NousResearch Hermes 3 Llama 3.1 8B](https://huggingface.co/NousResearch/Hermes-3-Llama-3.1-8B) models.

## Included Providers

| Provider | Description |
|----------|-------------|
| `HermesMediumUntrained` | Base provider for Hermes 3 Q4_K_M GGUF. Tools in `<tools>` XML, `<tool_call>` output format. |
| `HermesMediumTrained` | For LoRA-trained Hermes with date-key extraction baked in. Simplified date rules. |
| `HermesCompressed` | Compact prompt variant — first-sentence tool listing, DT_KEYS injection. |
| `HermesMediumMlx` | MLX 4-bit quantization variant with type normalization (array/int coercion). |

## Install

Via Jarvis admin or API:

```
POST /api/v0/prompt-providers/install
{"github_repo_url": "https://github.com/alexberardi/jarvis-pp-hermes"}
```

## Configuration

After install, set the active provider via settings:

```
llm.interface = HermesMediumUntrained
```

## Model Details

- **Family**: NousResearch Hermes 3 (Llama 3.1 8B base)
- **Format**: GGUF (Q4_K_M recommended) or MLX 4-bit
- **Tool calling**: Text-based `<tool_call>` XML tags (not native structured)
- **Size tier**: Medium (7B-13B)
