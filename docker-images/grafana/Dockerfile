FROM ubuntu

LABEL maintainer="Tania Arutiunian <tanyaharutyunyan01@gmail.com>"

WORKDIR /grafana

ARG GRAFANA_PORT=3000

RUN apt update && \
    apt upgrade -y && \
    apt install -y apt-transport-https software-properties-common wget && \
    wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key && \
    echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | tee -a /etc/apt/sources.list.d/grafana.list && \
    apt update && \
    apt install -y grafana

EXPOSE ${GRAFANA_PORT}

ENTRYPOINT ["grafana-server"]

CMD ["--config=/etc/grafana/grafana.ini", "--homepath=/usr/share/grafana"]