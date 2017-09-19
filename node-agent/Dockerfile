FROM cizer/bamboo-base-agent
RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash - && \
    apt-get install -y nodejs
RUN apt-get install -y npm