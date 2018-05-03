FROM kofonfor/adagios-git:latest
MAINTAINER alexclear@gmail.com

RUN \
  yum install -y java-1.8.0-openjdk && \
  curl -L -o /signal-cli-0.5.6.tar.gz https://github.com/AsamK/signal-cli/releases/download/v0.5.6/signal-cli-0.5.6.tar.gz && \
  cd /opt && tar zxf /signal-cli-0.5.6.tar.gz && \
  rm /signal-cli-0.5.6.tar.gz && \
  yum clean all

EXPOSE 80
# Livestatus remote service
EXPOSE 6557

VOLUME ["/data", "/etc/nagios", "/var/log/nagios", "/etc/adagios", "/opt/adagios", "/opt/pynag"]

ENTRYPOINT ["/config/bootstrap.sh"]
