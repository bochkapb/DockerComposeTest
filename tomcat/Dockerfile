FROM maven:latest AS Mymaven

ARG project_path
ARG project_workdir
RUN git clone $project_path
WORKDIR $project_workdir
RUN mvn package

FROM tomcat:8
ARG source_copy
ARG target_dir
COPY --from=Mymaven $source_copy $target_dir
RUN ls $target_dir