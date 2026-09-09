# DO NOT USE --> FROM ://microsoft.com
FROM mcr.microsoft.com/devcontainers/base:debian

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    build-essential \
    cmake \
    ninja-build \
    git \
    gcc-arm-none-eabi \
    libnewlib-arm-none-eabi \
    libstdc++-arm-none-eabi-newlib \
    python3

# Instantly pull the correct SDK version directly into the container's isolated workspace memory
RUN if [ ! -d "/tmp/pico-sdk/.git" ]; then \
        git clone -b 2.1.0 --recurse-submodules https://github.com/raspberrypi/pico-sdk.git /tmp/pico-sdk; \
    fi