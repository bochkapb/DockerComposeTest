FROM maven:latest AS maven

ARG project_path
ARG project_workdir
RUN git clone $project_path
WORKDIR $project_workdir
RUN mvn package

FROM tomcat:8
ARG source_copy
ARG target_dir
COPY --from=maven $source_copy $target_dir