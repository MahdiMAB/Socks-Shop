# Utiliser l'image Alpine officielle
FROM alpine:3.16

# Installer les dépendances nécessaires
RUN apk add --no-cache \
    curl \
    ca-certificates \
    && update-ca-certificates

# Installer kubectl
RUN curl -LO https://dl.k8s.io/release/v1.25.6/bin/linux/amd64/kubectl && \
    chmod +x kubectl && \
    mv kubectl /usr/local/bin/

# Définir un répertoire de travail
WORKDIR /workspace

# Entrée par défaut
CMD ["sh"]
