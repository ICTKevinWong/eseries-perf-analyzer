ARG TAG=latest
ARG PROJ_NAME=ntap-grafana
FROM ${PROJ_NAME}-plugin/eseries_monitoring/python-base
ENV COLLECTION_INTERVAL=30
ENV RETENTION_PERIOD=52w
ENV PROXY_ADDRESS=webservices:8080
RUN pip install -r requirements.txt && rm -rf /root/.cache

ADD docker-entrypoint.sh config.json *.py ./
RUN chmod +x *.sh *.py

ENTRYPOINT ["./docker-entrypoint.sh"]