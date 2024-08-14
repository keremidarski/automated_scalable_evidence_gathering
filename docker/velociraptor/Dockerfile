FROM ubuntu:20.04

RUN apt-get update && apt-get install -y wget

RUN wget https://github.com/Velocidex/velociraptor/releases/download/v0.6.6/velociraptor-v0.6.6-linux-amd64 -O /usr/local/bin/velociraptor
RUN chmod +x /usr/local/bin/velociraptor

COPY server.config.yaml /etc/velociraptor/server.config.yaml

ENTRYPOINT ["velociraptor", "--config", "/etc/velociraptor/server.config.yaml", "gui"]
