FROM            ubuntu:18.04

MAINTAINER      Dagin Wu <daginwu@gmail.com>

ADD             config.json /

RUN             apt-get update && apt-get install -y wget && apt-get install -y gnupg && \
                wget -qO - https://facebook.github.io/mcrouter/debrepo/bionic/PUBLIC.KEY | apt-key add - && \
                echo 'deb https://facebook.github.io/mcrouter/debrepo/bionic bionic contrib' >> /etc/apt/sources.list && \
                apt-get update && apt-get install -y mcrouter 

CMD             mcrouter --config-file=config.json -p 5000

EXPOSE          5000

