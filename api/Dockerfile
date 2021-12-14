FROM ubuntu

ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64

RUN apt-get update
RUN apt-get install -y openjdk-11-jdk
RUN apt-get install -y maven
RUN apt-get install software-properties-common -y
RUN add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"

# install git 
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git

# clone project and install opencv 
RUN git clone https://github.com/KarimOugueur/doodlestudent.git

WORKDIR /doodlestudent/api

RUN mvn clean package -Dquarkus.package.type=uber-jar -Dmaven.test.skip=true

EXPOSE 9001

CMD ["java", "-jar", "/doodlestudent/api/target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar"]
