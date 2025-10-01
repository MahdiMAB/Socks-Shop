FROM python:3-slim-bullseye

## Installation de curl, git et build-base
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    git \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

## Installation de Checkov
RUN pip3 install checkov

RUN mkdir -p /workspace

WORKDIR /workspace

CMD ["sh"]
