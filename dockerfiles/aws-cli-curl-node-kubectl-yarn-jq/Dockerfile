# Utiliser une image Debian avec Node.js préinstallé pour simplifier
FROM node:18-bullseye-slim

# Installer les dépendances système
RUN apt-get update && \
    apt-get install -y \
    curl \
    unzip \
    ca-certificates \
    jq \
    && rm -rf /var/lib/apt/lists/*

# Installer AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install && \
    rm -rf awscliv2.zip aws/

# Installer kubectl (version spécifique)
RUN curl -LO "https://dl.k8s.io/release/v1.25.6/bin/linux/amd64/kubectl" && \
    install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl && \
    rm kubectl

# Installer Yarn (via corepack pour la version moderne)
RUN corepack enable && \
    corepack prepare yarn@stable --activate

# Vérifier les installations
RUN aws --version && \
    node --version && \
    yarn --version && \
    kubectl version --client --short

# Définir un répertoire de travail
WORKDIR /workspace

# Entrée par défaut
CMD ["sh"]
