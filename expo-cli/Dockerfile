# ubuntu based image
FROM ubuntu:latest

# metadata
LABEL maintainer="chiefbark" description="Ubuntu based image with git, node, npm and expo-cli installed"

SHELL ["/bin/bash", "-c"]

WORKDIR /usr/src

# update system & install required
RUN apt-get update -y \
	&& apt-get install -y git curl

# env variable to set the nodejs version. See https://github.com/nodesource/distributions#debinstall
ARG node_version=lts
ENV ENV_NODE_VERSION $node_version

# install node & npm and install expo-cli
RUN curl -sL https://deb.nodesource.com/setup_$ENV_NODE_VERSION.x | bash \
	&& apt-get install -y nodejs \
	&& npm i -g --unsafe-perm expo-cli

ENTRYPOINT expo init . && /bin/bash