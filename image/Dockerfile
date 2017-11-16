FROM ubuntu:17.10
MAINTAINER Xiangmin Jiao <xmjiao@gmail.com>

COPY . /bd_build

# Disable syslog, cron, and sshd
RUN export DISABLE_SYSLOG=1 && \
  export DISABLE_CRON=1 && \
  export DISABLE_SSHD=1 && \
  /bd_build/prepare.sh && \
	/bd_build/system_services.sh && \
	/bd_build/utilities.sh && \
	/bd_build/cleanup.sh

ENV DEBIAN_FRONTEND="teletype" \
    LANG="en_US.UTF-8" \
    LANGUAGE="en_US:en" \
    LC_ALL="en_US.UTF-8"

CMD ["/sbin/my_init"]
