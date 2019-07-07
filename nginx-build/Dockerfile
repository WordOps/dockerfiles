FROM ubuntu:bionic

LABEL maintainer="Thomas SUCHON <thomas@virtubox.net>"

RUN apt-get update && apt-get install -qqy wget

RUN wget http://download.opensuse.org/repositories/openSUSE:Tools/xUbuntu_18.04/Release.key \
    && apt-key add - < Release.key

RUN sh -c "echo 'deb http://download.opensuse.org/repositories/openSUSE:/Tools/xUbuntu_18.04/ /' > /etc/apt/sources.list.d/osc.list"

RUN apt-get update && apt-get install -qqy \
                      debhelper \
                      devscripts \
                      dh-make \
                      dh-systemd \
                      dput \
                      git \
                      gnupg-agent \
                      osc \
                      sudo \
                      nano && \
		      apt-get autoremove --yes --purge && \
                      apt-get clean && \
                      rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY oscrc /root/.oscrc
