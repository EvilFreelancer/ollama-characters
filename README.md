# OLLaMA characters

Simple API chat based on [ollama](https://ollama.com) with historical characters.

## How to install

Install `ollama` cli tool:

```shell
curl -fsSL https://ollama.com/install.sh | sh
```

Download basic model:

```shell
ollama pull starling-lm:7b
```

## Build characters

```shell
ollama create yakovlev -f ./characters/yakovlev.Modelfile
ollama create chapaev -f ./characters/chapaev.Modelfile
```

## Start API server

```shell
ollama serve
```

HTTP server will be available on http://127.0.0.1:11434

Details about OLLaMA API server is [here](https://github.com/ollama/ollama/blob/main/docs/api.md).

## How to make an HTTP calls

```shell
curl -X POST http://127.0.0.1:11434/api/generate --data '{"model":"yakovlev","prompt":"Привет! Кто ты?","stream":false}'
curl -X POST http://127.0.0.1:11434/api/generate --data '{"model":"chapaev","prompt":"Привет! Кто ты?","stream":false}'
```
