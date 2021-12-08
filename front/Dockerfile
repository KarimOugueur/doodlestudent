FROM ubuntu

ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64

RUN apt-get update
RUN apt-get install -y openjdk-11-jdk
RUN apt-get install -y maven
RUN sudo apt-get install -y npm
RUN apt-get install software-properties-common -y
RUN add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"


# install git 
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git

# clone project and install opencv 
RUN git clone https://github.com/KarimOugueur/doodlestudent.git

WORKDIR /doodlestudent/front

RUN npm update 
RUN npm start  
RUN ng build