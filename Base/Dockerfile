FROM debian:buster-slim
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update; apt-get -y dist-upgrade

# Set locales
RUN echo locales locales/locales_to_be_generated select en_US.UTF-8 | debconf-set-selections;\
    echo locales locales/default_environment_locale select en_US.UTF-8 | debconf-set-selections;\
    export LANGUAGE="en_US.UTF-8";\
    echo 'LANGUAGE="en_US.UTF-8"' >> /etc/default/locale;\
    echo 'LC_ALL="en_US.UTF-8"' >> /etc/default/locale;\
    apt-get install -y locales;\
    locale-gen

# Install base packages
RUN apt-get install -y vim sudo procps net-tools nano bind9utils ca-certificates man curl \
aptitude apt-file debconf-utils iputils-ping dnsutils emacs-nox iproute2 openssh-client;\
apt-file update

# Make Python3.7 as default
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3.7; \
  update-alternatives --config python

CMD sleep infinity
