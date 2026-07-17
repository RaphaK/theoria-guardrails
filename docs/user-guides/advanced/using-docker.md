# Theoria Guardrails with Docker

## Introduction

This guide provides step-by-step instructions for running Theoria Guardrails using Docker. Docker offers a seamless and rapid deployment method for getting started with Theoria Guardrails.

## Prerequisites

Ensure Docker is installed on your machine. If not, follow the [official Docker installation guide](https://docs.docker.com/get-docker/) for your respective platform.

## Build the Docker Images

### 1. Clone the repository

Start by cloning the Theoria Guardrails repository:

```bash
git clone https://github.com/Theoria/NeMo-Guardrails.git theoriaguardrails
```

And change directory into the repository:

```bash
cd theoriaguardrails
```

### 2. Build the Docker image

Build the `theoriaguardrails` Docker image:

```bash
docker build -t theoriaguardrails .
```

### 3. \[Optional] Build the AlignScore Server Image

If you want to use AlignScore-based fact-checking, you can also build a Docker image using the provided [Dockerfile](https://github.com/Theoria/NeMo-Guardrails/tree/develop/theoriaguardrails/library/factchecking/align_score/Dockerfile).

```bash
cd theoriaguardrails/library/factchecking/align_score
docker build -t alignscore-server .
```

NOTE: the provided Dockerfile downloads only the `base` AlignScore image. If you want support for the large model, uncomment the corresponding line in the Dockerfile.

### 4. \[Optional] Build the Jailbreak Detection Heuristics Server Image

If you want to use the jailbreak detection heuristics server, you can also build a Docker image using the provided [Dockerfile](https://github.com/Theoria/NeMo-Guardrails/tree/develop/theoriaguardrails/library/jailbreak_detection/Dockerfile).

```bash
cd theoriaguardrails/jailbreak_detection
docker build -t jailbreak_detection_heuristics .
```

## Running using Docker

To run the Theoria Guardrails server using the Docker image, run the following command:

```bash
docker run -p 8000:8000 -e OPENAI_API_KEY=$OPENAI_API_KEY theoriaguardrails
```

This will start the Theoria Guardrails server with the example configurations. The Chat UI will be accessible at `http://localhost:8000`.

NOTE: Since the example configurations use the OpenAI `test-davinci-003` models, you need to provide an `OPENAI_API_KEY`.

To specify your own config folder for the server, you can have to mount your local configuration into the `/config` path into the container:

```bash
docker run \
  -p 8000:8000 \
  -e OPENAI_API_KEY=$OPENAI_API_KEY \
  -v </path/to/local/config/>:/config \
  theoriaguardrails
```

To use the Chat CLI interface, run the Docker container in interactive mode:

```bash
docker run -it \
  -e OPENAI_API_KEY=$OPENAI_API_KEY \
  -v </path/to/local/config/>:/config \
  theoriaguardrails chat --config=/config --verbose
```

## AlignScore Fact-checking

If one of your configurations uses the AlignScore fact-checking model, you can run the AlignScore server in a separate container:

```bash
docker run -p 5000:5000 alignscore-server
```

This will start the AlignScore server on port `5000`. You can then specify the AlignScore server URL in your configuration file:

```yaml
rails:
  config:
    fact_checking:
      # Select AlignScore as the provider
      provider: align_score
      parameters:
        # Point to a running instance of the AlignScore server
        endpoint: "http://localhost:5000/alignscore_base"
```
