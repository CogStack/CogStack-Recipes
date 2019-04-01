################################
#
# GATE Service Runner with ANNIE plugins
#
FROM gate-nlp-service:latest

# copy the GATE Bio-Yodie application
WORKDIR /gate/app/bioyodie
COPY ./applications/bio-yodie/gate /gate/app/bioyodie

# copy the bio-yodie UMLS resources
# INFO: this needs to be prepared manually due to licensing issues
COPY ./applications/bio-yodie/bio-yodie-resources /gate/app/bioyodie/bio-yodie-resources

# copy the Java Spring application with helper scripts
WORKDIR /app/nlp-service
COPY ./applications/bio-yodie/config /app/nlp-service/config
COPY ./common/run.sh /app/nlp-service/run.sh
COPY ./common/init_gate.sh /app/nlp-service/init_gate.sh

# run the initialization of GATE Embedded to download necessary plugins
RUN ["bash", "init_gate.sh"]
