FROM openjdk:11-bullseye

LABEL maintainer="loyayz - https://loyayz.com"

ENV CMAK_VERSION "3.0.0.6"
ENV ZK_HOSTS="zookeeper:2181"

RUN cd / \
      && wget -q https://github.com/yahoo/CMAK/releases/download/$CMAK_VERSION/cmak-$CMAK_VERSION.zip \
      && unzip cmak-$CMAK_VERSION.zip \
      && mv cmak-$CMAK_VERSION cmak \
      && rm -f cmak-$CMAK_VERSION.zip

EXPOSE 9000

WORKDIR /cmak

ENTRYPOINT ./bin/cmak -Dconfig.file=/cmak/conf/application.conf
