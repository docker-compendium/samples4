FROM eclipse-temurin:20

ENV VALIDATOR_VERSION=20.6.30

WORKDIR /src

ADD wget "https://github.com/validator/validator/releases/download/$VALIDATOR_VERSION/vnu.jar_$VALIDATOR_VERSION.zip" /src/vnu.jar.zip
RUN unzip /src/vnu.jar.zip \
  && rm /src/vnu.jar.zip

EXPOSE 8888
RUN adduser -S validator
USER validator
WORKDIR /home/validator
ENTRYPOINT ["java", "-jar", "/src/vnu.jar" ]
CMD ["--help"]
