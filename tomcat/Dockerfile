FROM maven:latest AS maven

ARG project_path
RUN git clone $project_path
WORKDIR boxfuse-sample-java-war-hello
RUN mvn package

FROM tomcat:8
COPY --from=maven /boxfuse-sample-java-war-hello/target/hello-1.0.war /usr/local/tomcat/webapps/