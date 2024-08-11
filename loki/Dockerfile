FROM ubuntu:latest as builder

# 安装 curl 和 gomplate
RUN apt-get update && apt-get install -y curl && \
    curl -L https://github.com/hairyhenderson/gomplate/releases/download/v3.8.0/gomplate_linux-amd64-slim -o /usr/local/bin/gomplate && \
    chmod +x /usr/local/bin/gomplate

COPY ./loki-config.yaml.template /tmp/loki-config.yaml.template


FROM grafana/loki:latest


COPY --from=builder /usr/local/bin/gomplate /usr/local/bin/gomplate
COPY --from=builder /tmp/loki-config.yaml.template /etc/loki/loki-config.yaml.template

ENTRYPOINT ["sh", "-c", "/usr/local/bin/gomplate -f /etc/loki/loki-config.yaml.template -o /etc/loki/config.yaml && /usr/bin/loki -config.file=/etc/loki/config.yaml"]

EXPOSE 3100