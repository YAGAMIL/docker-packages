FROM python:3.9.1
#FROM python:3.9.1-alpine3.12
#FROM python:3.9.1-slim-buster

COPY jdk-11.0.9 /usr/local/jdk-11.0.9
ENV JAVA_HOME=/usr/local/jdk-11.0.9
#COPY java-11-alibaba-dragonwell /usr/local/java-11-alibaba-dragonwell
#ENV JAVA_HOME=/usr/local/java-11-alibaba-dragonwell

#RUN echo '$export JAVA_HOME=/usr/local/jdk-11.0.9' /etc/profile && \
#    echo '$export PATH=${JAVA_HOME}/bin:$PATH' /etc/profile && \
#    source /etc/profile && \
#    java -version

ENV PATH=${JAVA_HOME}/bin:$PATH
#RUN python --version
RUN pip config set global.index-url https://pypi.doubanio.com/simple/ \
    && pip config set global.trusted-host pypi.doubanio.com  \
    && pip install Mako requests pymatgen apscheduler
RUN mkdir -p /jdks \
    && curl -SL https://download.java.net/openjdk/jdk11/ri/openjdk-11+28_linux-x64_bin.tar.gz \
    | tar -xJC /jdks