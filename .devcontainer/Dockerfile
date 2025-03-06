FROM node:20

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    curl \
    zip \
    unzip \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*