FROM node:18-bullseye-slim

# Install curl and tar
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    tar \
    unzip \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Set Velero version
ENV VELERO_VERSION=v1.12.3

# Download and install Velero
RUN curl -LO https://github.com/vmware-tanzu/velero/releases/download/${VELERO_VERSION}/velero-${VELERO_VERSION}-linux-amd64.tar.gz \
    && tar -xzf velero-${VELERO_VERSION}-linux-amd64.tar.gz \
    && mv velero-${VELERO_VERSION}-linux-amd64/velero /usr/local/bin/velero \
    && rm -rf velero-${VELERO_VERSION}-linux-amd64*

# Installer AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2.zip aws/

# Set default command to shell
CMD ["sh"]
