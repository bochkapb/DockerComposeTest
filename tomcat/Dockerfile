FROM maven:latest AS maven
RUN apt-get update
#RUN apt-get install -y git
RUN git clone ${PROJECT_PATH}
WORKDIR boxfuse-sample-java-war-hello
RUN mvn package

FROM tomcat:8
COPY --from=maven /boxfuse-sample-java-war-hello/target/hello-1.0.war /usr/local/tomcat/webapps/