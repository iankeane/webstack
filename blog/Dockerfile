FROM ubuntu:20.04

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y git
RUN apt-get install -y wget

RUN wget https://github.com/gohugoio/hugo/releases/download/v0.110.0/hugo_extended_0.110.0_Linux-64bit.tar.gz
RUN tar -xf hugo_extended_0.110.0_Linux-64bit.tar.gz

RUN mv hugo /usr/bin

RUN hugo new site /src

COPY . /src
RUN git clone https://github.com/panr/hugo-theme-terminal.git /src/themes/terminal

WORKDIR /src
RUN hugo

ENTRYPOINT ["hugo", "server", "--bind", "0.0.0.0"]
