FROM esolang/build-base

ENV BUILD_PACKAGES="db-dev" \
    RUNTIME_PACKAGES="db gmp-dev"

RUN apk add --update $BUILD_PACKAGES $RUNTIME_PACKAGES && \
    cd /tmp && \
    curl -m $TIMEOUT https://sourceforge.net/projects/open-cobol/files/gnu-cobol/3.0/gnucobol-3.0-rc1.tar.gz -LO && \
    tar xf gnucobol-3.0-rc1.tar.gz && \
    cd gnucobol-3.0-rc1 && \
    ./configure && \
    make && \
    make install && \
    apk del $BUILD_PACKAGES && \
    rm -rf /var/cache/apk/* /tmp/* && \
    ln -s /bin/script /bin/cobol

COPY script /root/script
