FROM debian:stable-slim
## docker build -f Debian-Dockerfile -t oci-cli:latest .

ENV DEBIAN_FRONTEND noninteractive
ENV SHELL /bin/bash
ENV TZ America/Sao_Paulo

RUN apt update && apt install -y libssl-dev libffi-dev python3-dev build-essential curl wget python3-pip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/cache/apt/archive/*.deb

COPY requirements.txt /requirements.txt

RUN python3 -m pip install --no-cache-dir --upgrade pip --break-system-packages \
    && python3 -m pip install --no-cache-dir -r /requirements.txt --break-system-packages \
    && oci --help

