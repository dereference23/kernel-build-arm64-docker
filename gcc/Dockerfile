FROM ubuntu:rolling

RUN apt-get update && apt-get install -y --no-install-recommends \
    bc \
    bison \
    ca-certificates \
    ccache \
    coreutils \
    cpio \
    curl \
    flex \
    gcc \
    gcc-12-aarch64-linux-gnu \
    gcc-12-arm-linux-gnueabi \
    git \
    lftp \
    libssl-dev \
    libc6-dev \
    libncurses-dev \
    make \
    openssh-client \
    python2 \
    xxd \
    xz-utils \
    zip \
 && rm -rf /var/lib/apt/lists/*

RUN ccache -M 1G -o compression=true \
 && update-alternatives --install /usr/bin/aarch64-linux-gnu-gcc aarch64-linux-gnu-gcc /usr/bin/aarch64-linux-gnu-gcc-12 120 \
 && update-alternatives --install /usr/bin/arm-linux-gnueabi-gcc arm-linux-gnueabi-gcc /usr/bin/arm-linux-gnueabi-gcc-12 120

ENV ARCH arm64
ENV CROSS_COMPILE aarch64-linux-gnu-
ENV CROSS_COMPILE_ARM32 arm-linux-gnueabi-
ENV KBUILD_BUILD_HOST github.com
