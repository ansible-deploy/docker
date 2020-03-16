FROM jenkins/jenkins
USER root
#RUN apt-get install vim
RUN apt-get update
RUN apt install -y apt-transport-https
RUN apt-get install -y sudo
#RUN echo 'deb https://apt.dockerproject.org/repo debian-stretch main' >> /etc/apt/sources.list.d/docker.list
RUN apt-get update
#RUN apt-get install docker-engine --allow-unauthenticated -y
#RUN apt-get install docker-engine
RUN rm -rf /var/lib/apt/lists/*
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
#RUN curl -L https://github.com/docker/compose/releases/download/1.4.1/ docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose; chmod +x /usr/local/bin/docker-composie
RUN curl -L https://github.com/docker/compose/ docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose; chmod +x /usr/local/bin/docker-compose
RUN apt-get install git

USER jenkins
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
