FROM ubuntu:16.04

#install wget
RUN  apt-get update \
  && apt-get install -y wget

WORKDIR /home/main

COPY ./main .

RUN ["chmod", "+x", "./openvpn-install.sh"]

CMD ["./openvpn-install.sh"]
