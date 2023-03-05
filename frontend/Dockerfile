FROM node:19-alpine

ARG CUID=1000

RUN addgroup -g $CUID -S nodeuser && adduser -u $CUID -S nodeuser -G nodeuser
#RUN addgroup -g $CUID -S nodeuser && adduser -u $CUID -S nodeuser -G nodeuser
#RUN groupadd --gid $CUID node && useradd --uid $CUID --gid node --shell /bin/bash --create-home node

WORKDIR /home/nodeuser/app

COPY ./package.json .
COPY ./package-lock.json .

RUN yarn install

COPY . .

USER nodeuser
