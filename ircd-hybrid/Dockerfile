# ircd-hybrid
#
# VERSION               1.0.0

FROM debian:wheezy
MAINTAINER SeongJae Park "sj38.park@gmail.com"

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y nano dialog irssi ircd-hybrid supervisor

RUN rm /etc/ircd-hybrid/ircd.conf
ADD ircd.conf /etc/ircd-hybrid/ircd.conf
ADD ircd.motd /etc/ircd-hybrid/ircd.motd
RUN chmod 660 /etc/ircd-hybrid/ircd.conf
RUN chown irc:irc /etc/ircd-hybrid/ircd.conf

ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf
CMD /usr/bin/supervisord
