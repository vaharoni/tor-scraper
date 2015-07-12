FROM ubuntu:14.04
MAINTAINER Amit Aharoni <amit.sites@gmail.com>

# Upgrade system
RUN \
  apt-get update && \
  apt-get dist-upgrade -y --no-install-recommends && \
  apt-get autoremove -y && \
  apt-get clean

# Install packages
RUN \
  apt-get install -y --no-install-recommends supervisor privoxy tor tor-geoipdb torsocks && \
  apt-get autoremove -y && \
  apt-get clean

# Add custom supervisor config
ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

# Add custom config
ADD ./privoxy/config /etc/privoxy/config
ADD ./tor/torrc /etc/tor/torrc

# Ports
EXPOSE 8118
EXPOSE 9050
EXPOSE 9053

VOLUME /var/log/tor

ADD run /usr/local/bin/run

CMD ["/usr/local/bin/run"]




