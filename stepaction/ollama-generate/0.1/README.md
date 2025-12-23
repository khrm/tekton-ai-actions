# Ollama Generate StepAction

A reusable StepAction that encapsulates the logic to communicate with an Ollama server. It handles waiting for the server, pulling the specified model, and generating a text response.

## Parameters

- **model**: The name of the model (e.g., `tinyllama`).
- **prompt**: The prompt to send.
- **ollama-host**: The URL of the server (default: `http://localhost:11434`).

## Results

- **response**: The generated text.

## Usage in a Task

```yaml
steps:
  - name: ask-ollama
    ref:
      name: ollama-generate
    params:
      - name: model
        value: tinyllama
      - name: prompt
        value: "Hello!"
      - name: ollama-host
        value: "http://localhost:11434"
```
