FROM grafana/loki:latest

# 复制配置文件
COPY ./loki-config.yaml /etc/loki/config.yaml

# 设置启动命令
CMD ["-config.file=/etc/loki/config.yaml"]

EXPOSE 3100
