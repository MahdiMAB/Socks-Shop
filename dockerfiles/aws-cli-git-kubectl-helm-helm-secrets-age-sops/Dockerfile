# Utiliser une image Debian officielle
FROM debian:bullseye-slim

# Mettre à jour et installer les dépendances (avec apt au lieu d'apk)
RUN apt-get update && apt-get install -y \
    curl \
    git \
    ca-certificates \
    unzip \
    tar \
    gnupg \
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

# Installer le plugin helm-secrets (plugin pour décrypter les secrets cryptés, avec sops entre autres)
RUN helm plugin install https://github.com/jkroepke/helm-secrets --version v4.6.5

# Installer age
RUN curl -L "https://github.com/FiloSottile/age/releases/download/v1.2.1/age-v1.2.1-linux-amd64.tar.gz" | tar xz -C /tmp/ \
    && mv /tmp/age/age /usr/local/bin/age \
    && mv /tmp/age/age-keygen /usr/local/bin/age-keygen \
    && rm -rf /tmp/age/ # Nettoyer le dossier temporaire du tarball

# Installer sops
RUN curl -L "https://github.com/getsops/sops/releases/download/v3.10.2/sops-v3.10.2.linux.amd64" -o /usr/local/bin/sops \
    && chmod +x /usr/local/bin/sops

# Définir le répertoire de travail
WORKDIR /workspace

# Commande par défaut
CMD ["sh"]
