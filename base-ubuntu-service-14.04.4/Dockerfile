FROM ubuntu:14.04.4

# Prepare ubuntu
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN locale-gen en_GB en_GB.UTF-8
RUN apt-get install -y curl git man
RUN ln -sf /bin/bash /bin/sh

# Install supervisord
RUN apt-get install -y supervisor
RUN mkdir -p /var/log/supervisor

# Install node
ENV NODE_ENV production
ENV NODE_VERSION v6.3.0
RUN curl -L https://raw.githubusercontent.com/creationix/nvm/v0.31.2/install.sh | HOME=/root bash
RUN source /root/.nvm/nvm.sh && nvm install $NODE_VERSION
RUN ln -s /root/.nvm/versions/node/$NODE_VERSION/bin/node /usr/bin/node
RUN ln -s /root/.nvm/versions/node/$NODE_VERSION/bin/npm /usr/bin/npm

CMD /usr/bin/supervisord -n -c /etc/supervisor/supervisord.conf
