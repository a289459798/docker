FROM openjdk:8
VOLUME /tmp
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/target/app.jar", "--spring.profiles.active=prod"]
