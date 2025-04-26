FROM eclipse-temurin:18-jre-jammy

# Run as non-root user
RUN groupadd -g 322 lavalink && \
    useradd -r -u 322 -g lavalink lavalink

WORKDIR /opt/Lavalink

RUN chown -R lavalink:lavalink /opt/Lavalink

USER lavalink

# Lavalink.jar を GitHub からダウンロード
RUN wget https://github.com/lavalink-devs/Lavalink/releases/download/4.0.8/Lavalink.jar -O Lavalink.jar

ENTRYPOINT ["java", "-Djdk.tls.client.protocols=TLSv1.1,TLSv1.2", "-jar", "Lavalink.jar"]
