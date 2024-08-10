FROM grafana/grafana:latest

# 复制配置文件
COPY ./grafana.ini /etc/grafana/grafana.ini
COPY ./grafana-datasources.yaml /etc/grafana/provisioning/datasources/datasources.yaml

# 环境变量
ENV GF_AUTH_ANONYMOUS_ENABLED=false
ENV GF_AUTH_ANONYMOUS_ORG_ROLE=Admin
ENV GF_AUTH_DISABLE_LOGIN_FORM=false
ENV GF_PATHS_PROVISIONING=/etc/grafana/provisioning
ENV GF_FEATURE_TOGGLES_ENABLE=traceqlEditor

EXPOSE 3000