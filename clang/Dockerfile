FROM ubuntu

RUN apt-get update && apt-get install -y --no-install-recommends \
    bc \
    bison \
    ca-certificates \
    cpio \
    curl \
    flex \
    gcc \
    git \
    libssl-dev \
    libc6-dev \
    libncurses-dev \
    make \
    python2 \
    xxd \
    xz-utils \
    zip \
 && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/kdrag0n/proton-clang.git /toolchain --depth=1

ENV PATH /toolchain/bin:$PATH
ENV ARCH arm64
ENV CROSS_COMPILE aarch64-linux-gnu-
ENV CROSS_COMPILE_ARM32 arm-linux-gnueabi-
ENV KBUILD_BUILD_HOST github.com
