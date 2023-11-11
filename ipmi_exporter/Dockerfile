FROM debian:11-slim

ARG IPMI_EXPORTER_VERSION=1.6.1

RUN apt update && apt install -y sudo wget freeipmi-tools \
	&&  wget -O /tmp/ipmi_exporter.tar.gz https://github.com/prometheus-community/ipmi_exporter/releases/download/v${IPMI_EXPORTER_VERSION}/ipmi_exporter-${IPMI_EXPORTER_VERSION}.linux-amd64.tar.gz \
	&& tar -zxvf /tmp/ipmi_exporter.tar.gz -C /tmp \
	&& mv /tmp/ipmi_exporter-*/ipmi_exporter / \
	&& rm -rf /var/cache/apt/lists/* \
	&& rm -rf /tmp/*

CMD ["/ipmi_exporter", "--config.file", "/config.yml"]

