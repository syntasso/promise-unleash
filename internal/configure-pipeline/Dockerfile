FROM ghcr.io/syntasso/kratix-pipeline-utility:v0.0.1

LABEL org.opencontainers.image.authors "kratix@syntasso.io"
LABEL org.opencontainers.image.source https://github.com/syntasso/promise-unleash

RUN [ "mkdir", "/resources" ]
ADD resources/* "/resources/"
ADD execute-pipeline execute-pipeline
COPY dependencies /tmp/dependencies

CMD [ "sh", "-c", "./execute-pipeline" ]
ENTRYPOINT []
