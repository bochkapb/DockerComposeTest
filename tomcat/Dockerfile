FROM maven:latest AS maven

ARG project_path
ARG project_workdir
ARG source_copy
ARG target_dir
RUN git clone $project_path
WORKDIR $project_workdir
RUN mvn package

FROM tomcat:8
COPY --from=maven $source_copy $target_dir