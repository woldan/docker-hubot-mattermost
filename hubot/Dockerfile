FROM alpine:3.3

RUN apk add --update nodejs make gcc g++ \
 && npm install -g npm \
 && npm install -g yo generator-hubot \
 && adduser hubot -h /home/hubot -D -s /bin/sh

ENV HOME /home/hubot
USER hubot
WORKDIR /home/hubot

RUN yo hubot --adapter mattermost --name matterbot --defaults

ENV MATTERMOST_TOKEN 3bu6o5qzhp8z9fhhjta39o3xwy
ENV MATTERMOST_INCOME_URL http://192.168.99.100:8065/hooks/dc7oxmhg3byqmf8zfxdz67xxxr
ENV MATTERMOST_ENDPOINT /hubot/incoming
ENV MATTERMOST_HUBOT_USERNAME matterbot
ENV MATTERMOST_CHANNEL town-square

CMD ["-a", "mattermost"]
ENTRYPOINT ["./bin/hubot"]
EXPOSE 8080
