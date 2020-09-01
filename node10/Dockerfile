FROM node:10

MAINTAINER Yonel Meza Avila "ymeza@devsu.com"

RUN npm install -g pm2@latest

VOLUME ["/var/app"]
VOLUME ["/var/log/app"]

ADD start /var/start
CMD ["/var/start"]

# Expose most common port for node apps
EXPOSE 3000
