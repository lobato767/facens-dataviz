FROM ubuntu:18.04

RUN apt-get update 

RUN apt-get upgrade -y

RUN apt-get install htop vim wget curl openjdk-8-jdk python3-pip  -y

# nodejs 8
RUN curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
RUN apt-get install -y nodejs
