ARG HELM_VERSION=4.1.4@sha256:4b0bdd2cf18ff6bca12aba0b2c5671384dab5035c19c57f0c58b854a0baf65be
FROM alpine/helm:${HELM_VERSION}

ENV HELM_PLUGINS="/helm-plugins" 
ARG HELM_UNITTEST_VERSION=1.0.3

RUN apk update && apk add bash curl yq && \
  # The plugin installation using helm plugin install seems to fail, therefore manual install.
  # This may be easier in the future
  mkdir -p ${HELM_PLUGINS}/helm-unittest && \
  curl -L https://github.com/helm-unittest/helm-unittest/releases/download/v${HELM_UNITTEST_VERSION}/helm-unittest-linux-amd64-${HELM_UNITTEST_VERSION}.tgz --output ${HELM_PLUGINS}/helm-unittest-linux-amd64-${HELM_UNITTEST_VERSION}.tgz && \
  tar zxvf ${HELM_PLUGINS}/helm-unittest-linux-amd64-${HELM_UNITTEST_VERSION}.tgz -C ${HELM_PLUGINS}/helm-unittest && \
  rm ${HELM_PLUGINS}/helm-unittest-linux-amd64-${HELM_UNITTEST_VERSION}.tgz

WORKDIR /usr/app

COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["docker-entrypoint.sh"]

CMD [ "helm" ]
