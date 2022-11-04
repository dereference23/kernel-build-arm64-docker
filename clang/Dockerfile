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
    git \
    lftp \
    libssl-dev \
    libc6-dev \
    libgcc-12-dev \
    libncurses-dev \
    make \
    openssh-client \
    python3 \
    xxd \
    xz-utils \
    zip \
 && rm -rf /var/lib/apt/lists/*

RUN ccache -M 1G -o compression=true

RUN mkdir /toolchain && cd /toolchain \
 && curl https://commondatastorage.googleapis.com/chromium-browser-clang/Linux_x64/clang-llvmorg-16-init-9369-g87a20868-1.tgz | tar xz \
 && curl https://commondatastorage.googleapis.com/chromium-browser-clang/Linux_x64/llvmobjdump-llvmorg-16-init-9369-g87a20868-1.tgz | tar xz

ENV PATH /toolchain/bin:$PATH
ENV ARCH arm64
ENV CROSS_COMPILE aarch64-linux-gnu-
ENV CROSS_COMPILE_ARM32 arm-linux-gnueabi-
ENV CROSS_COMPILE_COMPAT arm-linux-gnueabi-
ENV KBUILD_BUILD_HOST github.com
