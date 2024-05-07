# Starting from the official Node.js image
FROM ubuntu:22.04

# install basic packages
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
    bash \
    gcc \
    jq \
    g++ \
    make \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p -m0755 /var/run/sshd

# symlink python3 to python
RUN ln -s /usr/bin/python3 /usr/bin/python

# install basic dependencies for CodeActAgent
RUN pip3 install --upgrade pip
RUN pip3 install jupyterlab notebook jupyter_kernel_gateway flake8

# Install NVM
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash

# Install Node.js v18
RUN /bin/bash -c "source $HOME/.nvm/nvm.sh && nvm install 18 && nvm alias default 18"

# Make Node.js available in the PATH
ENV PATH /root/.nvm/versions/node/v18.0.0/bin:$PATH