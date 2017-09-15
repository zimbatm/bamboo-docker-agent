FROM atlassian/bamboo-base-agent

RUN apt-get update && apt-get install -y \
  software-properties-common

RUN add-apt-repository ppa:openjdk-r/ppa && \
  apt-get update && \
  apt-get install -y openjdk-8-jdk \
  openjdk-8-jre

RUN echo 2 | update-alternatives --config java && \
  echo 2 | update-alternatives --config javac
