# Ollama Run

Run an Ollama Large Language Model (LLM) to generate a response for a prompt. This Task runs an Ollama server as a sidecar and executes the prompt against it.

## Parameters

- **model**: The name of the model to use (e.g., `llama2`, `tinyllama`).
- **prompt**: The prompt to send to the model.
- **ollama-image**: The container image for Ollama (default: `docker.io/ollama/ollama:latest`).

## Workspaces

- **ollama-cache**: Persistent storage for Ollama models (mounted at `/root/.ollama`).

## Usage

```yaml
apiVersion: tekton.dev/v1
kind: TaskRun
metadata:
  generateName: ollama-run-
spec:
  taskRef:
    name: ollama-run
  params:
    - name: model
      value: tinyllama
    - name: prompt
      value: "Why is the sky blue?"
  workspaces:
    - name: ollama-cache
      emptyDir: {}
```
