FROM node:15.2.1-alpine3.10
RUN mkdir -p /www/build
ADD index.js /www
ADD package.json /www
WORKDIR /www
RUN npm install
ENTRYPOINT ["node", "index.js"]