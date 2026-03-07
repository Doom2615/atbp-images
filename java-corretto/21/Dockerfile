FROM        amazoncorretto:25

LABEL       author="Doom2615" maintainer="doom@atbphosting.com"
LABEL       org.opencontainers.image.source="https://github.com/Doom2615/atbp-images"
LABEL       org.opencontainers.image.licenses="MIT"

RUN         yum upgrade -y \
            && yum install -y \
            curl ca-certificates openssl git tar sqlite fontconfig \
            freetype libstdc++ freetype-devel lsof tzdata iproute \
            gcc gcc-c++ automake make libtool \
            && yum clean all \
            && rm -rf /var/cache/yum \
            && useradd -m -d /home/container container

ENV         LC_ALL=en_US.UTF-8
ENV         LANG=en_US.UTF-8
ENV         LANGUAGE=en_US.UTF-8

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
