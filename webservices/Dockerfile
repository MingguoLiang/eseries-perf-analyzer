ARG TAG=latest
FROM netapp/eseries-webservices:3.10 as base
ADD wsconfig.xml ./wsconfig.xml

FROM ntap-grafana/alpine-base:${TAG}
WORKDIR /opt/netapp/webservices_proxy
RUN apk add openjdk8-jre
COPY --from=base /opt/netapp/webservices_proxy ./
CMD ["./webserver.sh"]
