FROM prom/prometheus:latest

# 复制配置文件
COPY ./prometheus.yaml /etc/prometheus.yaml

# 设置启动命令
CMD ["--config.file=/etc/prometheus.yaml", "--web.enable-remote-write-receiver", "--enable-feature=exemplar-storage"]


EXPOSE 9090
