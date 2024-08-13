FROM grafana/pyroscope:latest

COPY ./pyroscope.yml /etc/pyroscope.yml

CMD ["-config.file=/etc/pyroscope.yml"]

EXPOSE 4040