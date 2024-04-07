FROM ubuntu

LABEL maintainer="Tania Arutiunian <tanyaharutyunyan01@gmail.com>"

WORKDIR /node-exporter

ARG FORMAT=amd64
ARG NODE_EXPORTER_PORT=9100
ARG VERSION=1.5.0

ADD https://github.com/prometheus/node_exporter/releases/download/v${VERSION}/node_exporter-${VERSION}.linux-${FORMAT}.tar.gz .

RUN tar xvfz node_exporter-${VERSION}.linux-${FORMAT}.tar.gz node_exporter-${VERSION}.linux-${FORMAT} && \
    mv node_exporter-${VERSION}.linux-${FORMAT}/node_exporter /usr/local/bin && \
    rm -r node_exporter-${VERSION}.linux-${FORMAT}*

EXPOSE ${NODE_EXPORTER_PORT}

ENTRYPOINT ["/usr/local/bin/node_exporter"]