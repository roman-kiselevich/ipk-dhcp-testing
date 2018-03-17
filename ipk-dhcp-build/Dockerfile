FROM ubuntu:latest

RUN apt-get update \
    && apt-get install -y vim isc-dhcp-server isc-dhcp-client net-tools 

# just dhcp server configure magic 
RUN echo INTERFACES=\"eth0\" > etc/default/isc-dhcp-server

# just dhcp server configure magic 
RUN echo "subnet 192.168.42.32 netmask 255.255.255.240 {" \
         "range   192.168.42.33   192.168.42.41;"         \
         "range   192.168.42.43   192.168.42.46;"         \
         "}" > /etc/dhcp/dhcpd.conf

RUN echo "while true; do sleep 999999; done" > entrypoint.sh