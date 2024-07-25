FROM ubuntu:20.04

RUN apt-get update && apt-get install -y wget

# Download GRR
RUN wget https://github.com/google/grr/releases/download/v3.4.0.4/grr-server_3.4.0.4_amd64.deb -O /tmp/grr-server.deb
RUN wget https://github.com/google/grr/releases/download/v3.4.0.4/grr-client_3.4.0.4_amd64.deb -O /tmp/grr-client.deb

# Install GRR server
RUN apt-get install -y /tmp/grr-server.deb

# Install GRR client
RUN apt-get install -y /tmp/grr-client.deb

ENTRYPOINT ["grr_server"]
