FROM ubuntu:20.04

USER root
ARG UID=1000
ARG GID=1000
RUN groupadd -g ${GID} app && \
    useradd -u ${UID} -m app -g app && \
    apt-get update && \
    apt-get install curl git nano -y && \
    curl -fsSL https://code-server.dev/install.sh | sh

USER app
ARG NODE_VERSION=16.13.0
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash && \
    export NVM_DIR="$HOME/.nvm" && \
    . $NVM_DIR/nvm.sh && \
    nvm install ${NODE_VERSION}
