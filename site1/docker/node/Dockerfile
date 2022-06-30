FROM node:current-slim

RUN apt-get update && \
    apt install -y sudo

RUN adduser --disabled-password --gecos '' locachampion
RUN adduser locachampion sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER locachampion

WORKDIR /home/locachampion/code/

COPY --chown=locachampion:locachampion package.json package.json
COPY --chown=locachampion:locachampion . .

RUN sudo chown -R locachampion:locachampion .

RUN yarn
