FROM openjdk:13-jdk-alpine3.9
VOLUME /tmp
COPY build/libs/app.jar app.jar
EXPOSE 5000
#The APP_ENV variable can be DEV, UAT and PROD
ENV APP_ENV=${APP_ENV}
ENTRYPOINT ["java", "-jar","-Dspring.profiles.active=${APP_ENV}", "/app.jar"]
