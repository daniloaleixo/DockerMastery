FROM node:10.18.1-alpine3.11

EXPOSE 3000

RUN apk add --update tini
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package.json /usr/src/app
RUN npm install
RUN npm cache clean --force
COPY . /usr/src/app

CMD ["/sbin/tini", "--", "node", "./bin/www"]
