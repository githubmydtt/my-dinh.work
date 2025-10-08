# Use latest Ubuntu image
FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Install Hugo Extended
RUN apt-get update && apt-get install -y wget \
    && HUGO_VERSION="0.151.0" \
    && wget https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
    && dpkg -i hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
    && rm hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
    && apt-get clean

# Install Node.js for theme tooling
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
    && apt-get install -y nodejs

# Set working directory
WORKDIR /workspace

# Expose Hugo dev server port
EXPOSE 1313