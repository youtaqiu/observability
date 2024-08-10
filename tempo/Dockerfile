FROM ubuntu:latest as builder

# 安装 curl 和 gomplate
RUN apt-get update && apt-get install -y curl && \
    curl -L https://github.com/hairyhenderson/gomplate/releases/download/v3.8.0/gomplate_linux-amd64-slim -o /usr/local/bin/gomplate && \
    chmod +x /usr/local/bin/gomplate

COPY ./tempo-s3.yaml.template /tmp/tempo-s3.yaml.template


FROM grafana/tempo:latest

USER root

COPY --from=builder /usr/local/bin/gomplate /usr/local/bin/gomplate
COPY --from=builder /tmp/tempo-s3.yaml.template /etc/tempo-s3.yaml.template

ENTRYPOINT ["sh", "-c", "/usr/local/bin/gomplate -f /etc/tempo-s3.yaml.template -o /etc/tempo.yaml && /tempo -config.file=/etc/tempo.yaml"]

EXPOSE 4318
