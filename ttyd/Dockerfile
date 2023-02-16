FROM debian:11

WORKDIR /app
RUN apt update
RUN apt install -y build-essential
RUN apt install -y cmake
RUN apt install -y git
RUN apt install -y libjson-c-dev
RUN apt install -y libwebsockets-dev
RUN apt install -y htop
RUN apt install -y nano
RUN git clone https://github.com/tsl0922/ttyd.git

WORKDIR /app/ttyd/build

COPY ./tmp.txt .

RUN cmake ..
RUN make
RUN make install

EXPOSE 8080

# ENTRYPOINT ["tail", "-f", "/dev/null"]
CMD ["ttyd", "-p", "8080", "nano", "tmp.txt"]
