FROM ubuntu:20.04

RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y git
RUN apt-get install -y yarn

WORKDIR /app
RUN git clone https://github.com/logseq/logseq
RUN wget "https://github.com/logseq/logseq/releases/tag/0.0.1-100" -P ./resources
WORKDIR /app/logseq
ENTRYPOINT ["tail", "-f", "/dev/null"]
# RUN yarn
# RUN yarn release

# ENTRYPOINT ["entrypoint.sh"]
