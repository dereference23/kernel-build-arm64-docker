FROM ubuntu

RUN apt-get update && apt-get install -y --no-install-recommends \
    bc \
    bison \
    ca-certificates \
    coreutils \
    cpio \
    curl \
    flex \
    gcc \
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

RUN git clone https://github.com/arter97/arm64-gcc.git /toolchain_64 --depth=1
RUN git clone https://github.com/arter97/arm32-gcc.git /toolchain_32 --depth=1

ENV PATH /toolchain_64/bin:/toolchain_32/bin:$PATH
ENV ARCH arm64
ENV CROSS_COMPILE aarch64-elf-
ENV CROSS_COMPILE_ARM32 arm-eabi-
ENV KBUILD_BUILD_HOST github.com
