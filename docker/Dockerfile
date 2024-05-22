##############
# Base Image #
##############

FROM rtvu/docker-ubuntu

########################
# Setup User Workspace #
########################

RUN \
  mkdir ${HOME}/workspace && \
  git config --global --add safe.directory ${HOME}/workspace

#################################
# Setup Development Environment #
#################################

ARG GO_VERSION=1.22.3

RUN \
  wget --output-document=go.tar.gz https://go.dev/dl/go${GO_VERSION}.linux-$(dpkg --print-architecture).tar.gz && \
  sudo tar --directory=/usr/local -xzf go.tar.gz && \
  echo "export PATH=$PATH:/usr/local/go/bin" >> ${HOME}/.profile && \
  rm go.tar.gz

###########
# Startup #
###########

WORKDIR ${HOME}/workspace

CMD ["/bin/bash"]
