# Docker image for the OpenAM configurator tool
FROM java:8

WORKDIR /var/tmp

# Download AM 13 configurator from maven build
RUN curl http://maven.forgerock.org/repo/simple/snapshots/org/forgerock/openam/openam-distribution-ssoconfiguratortools/13.0.0-SNAPSHOT/ \
   | grep -o 'href=.*\.zip\"' | grep -o 'openam.*zip' | \
 xargs -I % curl -o /var/tmp/configurator.zip  \
 http://maven.forgerock.org/repo/simple/snapshots/org/forgerock/openam/openam-distribution-ssoconfiguratortools/13.0.0-SNAPSHOT/%
RUN  unzip configurator.zip


COPY default.properties /var/tmp/
COPY config.sh /var/tmp/

CMD ["/var/tmp/config.sh"]
