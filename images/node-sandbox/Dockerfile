# Starting from the official Node.js image
FROM node:18

# Install some basic tools
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    git \
    vim \
    nano \
    unzip \
    zip \
    python3 \
    python3-pip \
    python3-venv \
    python3-dev \
    build-essential \
    openssh-server \
    sudo \
    && rm -rf /var/lib/apt/lists/*

RUN service ssh start
