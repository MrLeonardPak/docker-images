FROM golang:latest

ENV USER=$(whoami)

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Update & Upgrade
RUN apt-get update \
    && apt-get upgrade -y

# Install tools
RUN apt-get install -y \
    wget \
    git \
    vim \
    tree \
    bash-completion

RUN rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/MrLeonardPak/workspace-setup.git $HOME/workspace-setup \
    && $HOME/workspace-setup/setup-docker.bash
