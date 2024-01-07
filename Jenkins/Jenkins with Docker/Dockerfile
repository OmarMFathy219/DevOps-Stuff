FROM jenkins/jenkins:lts

USER root

# Update and install required packages
RUN apt-get update -qq && \
    apt-get install -qqy apt-transport-https ca-certificates curl gnupg2 software-properties-common

# Use Docker's official installation script
RUN curl -fsSL https://get.docker.com -o get-docker.sh
RUN sh get-docker.sh

# Clean up
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Add Jenkins user to the Docker group
RUN usermod -aG docker jenkins

USER jenkins
