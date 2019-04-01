################################
#
# GATE Service Runner with ANNIE plugins
#
FROM gate-nlp-service:latest

WORKDIR /gate/app/drug-app
COPY ./applications/drug-app/gate /gate/app/drug-app

WORKDIR /app/nlp-service
COPY ./applications/drug-app/config /app/nlp-service/config
COPY ./common/run.sh /app/nlp-service/run.sh
COPY ./common/init_gate.sh /app/nlp-service/init_gate.sh

RUN ["bash", "init_gate.sh"]
