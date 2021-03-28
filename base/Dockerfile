from ubuntu:20.04

RUN apt-get update && \
    apt-get install -y \
    bash curl net-tools \
    dnsutils iputils-ping

RUN curl -o /usr/local/bin/wait-for-it.sh \
    https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh \
    && chmod 755 /usr/local/bin/wait-for-it.sh

ENTRYPOINT [ "bash" ]
