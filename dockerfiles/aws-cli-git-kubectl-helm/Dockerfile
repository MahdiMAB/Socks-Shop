# Utiliser une image Debian officielle
FROM debian:bullseye-slim

# Mettre à jour et installer les dépendances (avec apt au lieu d'apk)
RUN apt-get update && apt-get install -y \
    curl \
    git \
    ca-certificates \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Installer AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2.zip aws/

# Installer kubectl
RUN curl -LO "https://dl.k8s.io/release/v1.25.6/bin/linux/amd64/kubectl" \
    && chmod +x kubectl \
    && mv kubectl /usr/local/bin/

# Installer Helm
RUN curl -L "https://get.helm.sh/helm-v3.8.2-linux-amd64.tar.gz" -o helm.tar.gz \
    && tar -zxvf helm.tar.gz \
    && mv linux-amd64/helm /usr/local/bin/ \
    && rm -rf linux-amd64 helm.tar.gz

# Définir le répertoire de travail
WORKDIR /workspace

# Commande par défaut
CMD ["sh"]
