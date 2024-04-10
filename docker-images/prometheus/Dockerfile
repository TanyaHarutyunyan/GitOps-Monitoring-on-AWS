FROM ubuntu

LABEL maintainer="Tania Arutiunian <tanyaharutyunyan01@gmail.com>"

WORKDIR /prometheus

ARG FORMAT=amd64
ARG PROMETHEUS_PORT=9090
ARG VERSION=2.37.6

ADD https://github.com/prometheus/prometheus/releases/download/v${VERSION}/prometheus-${VERSION}.linux-${FORMAT}.tar.gz .

RUN tar xvfz prometheus-${VERSION}.linux-${FORMAT}.tar.gz prometheus-${VERSION}.linux-${FORMAT} && \
    rm prometheus-${VERSION}.linux-${FORMAT}.tar.gz && \
    mkdir /etc/prometheus /var/lib/prometheus && cd prometheus-${VERSION}.linux-${FORMAT} && \
    mv prometheus promtool /usr/local/bin/ && mv consoles/ console_libraries/ /etc/prometheus/

EXPOSE ${PROMETHEUS_PORT}

ENTRYPOINT ["/usr/local/bin/prometheus"]

CMD ["--config.file=/etc/prometheus/prometheus.yml"]