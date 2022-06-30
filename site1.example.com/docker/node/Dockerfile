FROM node:current-slim

RUN apt-get update && \
    apt install -y sudo

RUN adduser --disabled-password --gecos '' travis
RUN adduser travis sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER travis

WORKDIR /home/travis/code/

COPY --chown=travis:travis package.json package.json
COPY --chown=travis:travis . .

RUN sudo chown -R travis:travis .

RUN yarn
