FROM ubuntu:22.04

RUN apt update && apt upgrade -y
RUN apt-get install rust-all cargo -y
RUN apt-get install python3 python3-pip python3.10-venv -y
RUN apt-get install golang-go -y
RUN apt-get install vim -y

WORKDIR /app

RUN mkdir -p $HOME/src
ENV CARGO_HOME=$HOME/.cargo
ENV GOROOT=/usr/lib/go
ENV PATH=$GOROOT/bin:$PATH
ENV PATH=$PATH:/usr/local/bin/rustc

# Combine all previous instructions
RUN apt-get update && \
    apt upgrade -y && \
    apt-get install -y rust-all cargo python3 python3-pip python3.10-venv golang-go vim && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set default command
CMD ["bash"]

