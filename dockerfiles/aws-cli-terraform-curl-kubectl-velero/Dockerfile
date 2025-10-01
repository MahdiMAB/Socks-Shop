FROM debian:bullseye-slim

## Installation des utilitaires et dépendances de base
RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-transport-https \
    ca-certificates \
    lsb-release \
    gnupg \
    curl \
    unzip \
    bash \
    jq \
    openjdk-17-jre-headless \
    libfuse2 \
    && rm -rf /var/lib/apt/lists/*

## Installation de l'AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2.zip aws

## Installation de Terraform
RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg \
    && echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/hashicorp.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends terraform \
    && rm -rf /var/lib/apt/lists/*

## Installation de kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" \
    && chmod +x kubectl \
    && mv kubectl /usr/local/bin/

## Installation de Velero CLI
ARG VELERO_VERSION="1.12.3"
RUN curl -LO "https://github.com/vmware-tanzu/velero/releases/download/v${VELERO_VERSION}/velero-v${VELERO_VERSION}-linux-amd64.tar.gz" \
    && tar -xzf velero-v${VELERO_VERSION}-linux-amd64.tar.gz \
    && mv velero-v${VELERO_VERSION}-linux-amd64/velero /usr/local/bin \
    && rm -rf velero-v${VELERO_VERSION}-linux-amd64.tar.gz velero-v${VELERO_VERSION}-linux-amd64

CMD ["sh"]
