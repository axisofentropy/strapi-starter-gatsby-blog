# Influenced by https://github.com/strapi/community-content/issues/813#issuecomment-1205095562
FROM node:16

ARG NODE_ENV=development
ENV NODE_ENV=${NODE_ENV}

WORKDIR /app

ADD ./package.json /app

ADD ./yarn.lock /app

RUN yarn config set network-timeout 600000 -g && yarn install --frozen-lockfile

ADD . /app

RUN yarn build

#RUN yarn seed

EXPOSE 1337

ENTRYPOINT ["/bin/sh", "-c"]

CMD ["yarn develop"]
