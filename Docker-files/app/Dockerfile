FROM openjdk:11 AS build_image

RUN apt update && \
    apt install -y maven git && \
    git clone https://github.com/devopshydclub/vprofile-project.git && \
    cd vprofile-project && \
    git switch docker && \
    mvn install

FROM tomcat:9-jre11

RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build_image /vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
