FROM ubuntu

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
    git \
    lftp \
    libssl-dev \
    libc6-dev \
    libncurses-dev \
    make \
    openssh-client \
    python2 \
    wget \
    xxd \
    xz-utils \
    zip \
 && rm -rf /var/lib/apt/lists/*

RUN wget -O toolchain_64.tar.xz "https://developer.arm.com/-/media/Files/downloads/gnu-a/10.2-2020.11/binrel/gcc-arm-10.2-2020.11-x86_64-aarch64-none-elf.tar.xz?revision=79f65c42-1a1b-43f2-acb7-a795c8427085&la=en&hash=3BEE623628664E6E1736ABBE7CE5AD76B65B51EA" \
 && tar -xf toolchain_64.tar.xz \
 && mkdir /toolchain_64 \
 && mv gcc-arm-10.2-2020.11-x86_64-aarch64-none-elf/* /toolchain_64 \
 && rm -rf gcc-arm-10.2-2020.11-x86_64-aarch64-none-elf \
 && rm toolchain_64.tar.xz

RUN wget -O toolchain_32.tar.xz "https://developer.arm.com/-/media/Files/downloads/gnu-a/10.2-2020.11/binrel/gcc-arm-10.2-2020.11-x86_64-arm-none-eabi.tar.xz?revision=76e7e20a-4334-4d3f-b9e6-66159eda6d62&la=en&hash=D0A07E98868062EC4959BFC71A7781397958983A" \
 && tar -xf toolchain_32.tar.xz \
 && mkdir /toolchain_32 \
 && mv gcc-arm-10.2-2020.11-x86_64-arm-none-eabi/* /toolchain_32 \
 && rm -rf gcc-arm-10.2-2020.11-x86_64-arm-none-eabi \
 && rm toolchain_32.tar.xz 

ENV PATH /toolchain_64/bin:/toolchain_32/bin:$PATH
ENV ARCH arm64
ENV CROSS_COMPILE aarch64-none-elf-
ENV CROSS_COMPILE_ARM32 arm-none-eabi-
ENV KBUILD_BUILD_HOST github.com
