FROM node:8

MAINTAINER Cesar Salazar "csalazar@devsu.com"

RUN npm install -g pm2@latest

VOLUME ["/var/app"]
VOLUME ["/var/log/app"]

ADD start /var/start
CMD ["/var/start"]

# Expose most common port for node apps
EXPOSE 3000