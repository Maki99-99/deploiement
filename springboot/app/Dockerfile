# Java 17 runtime (Spring Boot 3 requires Java 17 minimum)
FROM eclipse-temurin:17-jre

# Temporary folder used by Spring Boot / Tomcat
VOLUME /tmp

# Documents the port the app listens on (server.port=8081)
EXPOSE 8081

# Path of the jar built by Maven (can be overridden with --build-arg)
ARG JAR_FILE=target/demo-0.0.1.jar

# Copy the jar into the image, renamed app.jar
ADD ${JAR_FILE} app.jar

# Command run when the container starts
ENTRYPOINT ["java","-jar","/app.jar"]
