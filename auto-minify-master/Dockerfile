FROM node:current-alpine3.12

WORKDIR /app/

COPY package.json /app/package.json
COPY .babelrc /app/.babelrc

RUN apk add --no-cache bash coreutils \
 && apk add --no-cache --upgrade grep \
 && npm install
RUN npm i @babel/plugin-proposal-class-properties --save

ADD entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
