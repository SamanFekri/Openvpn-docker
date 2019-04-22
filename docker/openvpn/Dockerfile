FROM ubuntu:16.04

#install wget
RUN  apt-get update \
  && apt-get install -y wget

# enable TUN
RUN mkdir -p /dev/net \
  && mknod /dev/net/tun c 10 200 \
  && chmod 600 /dev/net/tun

WORKDIR /home/main

COPY ./main .

RUN ["chmod", "+x", "./openvpn-install.sh"]

CMD ["./openvpn-install.sh"]
