FROM openjdk:13-jdk-alpine3.9
VOLUME /tmp
ARG JAR_FILE=build/libs/app.jar
COPY ${JAR_FILE} app.jar
EXPOSE 5000
ENV APP_ENV=${APP_ENV}
ENTRYPOINT ["java", "-jar","-Dspring.profiles.active=${APP_ENV}", "/app.jar"]
