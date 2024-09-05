FROM node:22.8.0-bullseye

# Upgrade NPM
# node may come with an older version of npm. Ensure we have a specific npm.
RUN npm install -g npm@10.8.3


RUN apt-get update
RUN apt-get install -y \
   lsb-release \
   curl

RUN npm install -g typescript@5.5.4


COPY ps1.bash .
RUN cat ps1.bash >> /home/node/.bashrc && rm ps1.bash

COPY .bash_aliases /home/node/.bash_aliases


RUN echo 'git config core.hooksPath /workspace/.devcontainer/.githooks' >> ~/.bashrc