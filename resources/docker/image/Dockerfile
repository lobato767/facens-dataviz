FROM ubuntu:18.04

RUN apt-get update 

RUN apt-get upgrade -y

RUN apt-get install htop vim wget curl openjdk-8-jdk python3-pip  -y

# nodejs 8
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install -y nodejs git

# building the repo
RUN git clone https://github.com/matheusmota/dataviz2018
RUN pip3 install -r dataviz2018/binder/requirements.txt
RUN mkdir conda-bld
RUN sh dataviz2018/binder/postBuild

ENV LANG=C.UTF-8

# Expose Jupyter port & cmd
EXPOSE 8888
RUN mkdir -p /opt/app/data
RUN cp  dataviz2018  /opt/app/data/ -r
CMD jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root