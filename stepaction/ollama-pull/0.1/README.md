# Ollama Pull StepAction

A reusable StepAction that waits for an Ollama server to be ready and pulls a specified model.

## Parameters

- **model**: The name of the model to pull (e.g., `tinyllama`).
- **ollama-host**: The URL of the server (default: `http://localhost:11434`).

## Usage in a Task

```yaml
steps:
  - name: pull-model
    ref:
      name: ollama-pull
    params:
      - name: model
        value: tinyllama
      - name: ollama-host
        value: "http://localhost:11434"
```
