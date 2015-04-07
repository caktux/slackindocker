FROM ubuntu:utopic

ENV DEBIAN_FRONTEND noninteractive

# Usual update / upgrade
RUN apt-get update && apt-get upgrade -y && apt-get dist-upgrade -y

# Install our favorite vcs and other requirements
RUN apt-get install -y git curl wget vim supervisor

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup | bash -
RUN apt-get install --fix-missing -y nodejs

# Get slack-irc
RUN npm install -g slackin

# Add configurations
ADD config slackin/config

# Add startup script
ADD slackin.sh slackin.sh
RUN chmod a+x slackin.sh

# Add supervisor configs
ADD supervisord.conf supervisord.conf

EXPOSE 3000

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
