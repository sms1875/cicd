FROM jenkins/jenkins:lts

USER root

# 도커 CLI 
RUN apt-get update && \
    apt-get install -y docker.io docker-compose git curl && \
    rm -rf /var/lib/apt/lists/*

# Jenkins 플러그인 
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --plugin-file /usr/share/jenkins/ref/plugins.txt

# 기본 admin 계정 생성
COPY basic-security.groovy /usr/share/jenkins/ref/init.groovy.d/basic-security.groovy

USER jenkins