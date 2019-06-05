FROM openjdk:8
RUN \
  apt-get update && \
  apt-get install -y supervisor && \
  rm -rf /var/lib/apt/lists/* && \
  sed -i 's/^\(\[supervisord\]\)$/\1\nnodaemon=true/' /etc/supervisor/supervisord.conf
VOLUME VOLUME ["/etc/supervisor/conf.d", "/tmp"]
ENTRYPOINT ["nohup", "java","-Djava.security.egd=file:/dev/./urandom","-jar","/target/app.jar", "--spring.profiles.active=prod", ">/dev/null", "2>$1", "&"]
CMD ["supervisord", "-c", "/etc/supervisor/supervisord.conf"]
