FROM ubuntu:16.04

#install wget and sudo and apt-utils
RUN  apt-get update \
  && apt-get -y install apt-utils \
  && apt-get install -y wget \
  && apt-get -y install sudo


# enable TUN
RUN sudo mkdir -p /dev/net \
  && sudo mknod /dev/net/tun c 10 200 \
  && sudo chmod 600 /dev/net/tun

WORKDIR /home/main

COPY ./main .

RUN ["chmod", "+x", "./openvpn-install.sh"]

# tail -f /dev/null keeps container running after bash completed
CMD ./openvpn-install.sh && tail -f /dev/null
