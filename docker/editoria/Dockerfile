FROM node:7.10-alpine
MAINTAINER Vasilis Kefallinos <vkefallinos@gmail.com>
RUN apk update
RUN apk --no-cache add git curl
RUN apk --no-cache --update add tar
ENV INSTALL_PATH /editoria
RUN mkdir -p $INSTALL_PATH
WORKDIR $INSTALL_PATH
RUN  curl -L \
 https://gitlab.coko.foundation/editoria/editoria/repository/archive.tar.gz?ref=0.1.2 \
 | tar zx -C . --strip-components 1
RUN apk add --no-cache make gcc g++ python && \
  npm install --production && \
  apk del make gcc g++ python git curl
EXPOSE 3000:3000
CMD ["npm", "start"]