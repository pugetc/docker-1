FROM registry.access.redhat.com/jboss-webserver-3/webserver30-tomcat7-openshift

MAINTAINER warren.strange@gmail.com

ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
WORKDIR $CATALINA_HOME

EXPOSE 8080

# download openam nightly build war
# Trick taken from wadahiro/docker-openam-nightly!
RUN curl http://download.forgerock.org/downloads/openam/openam_link.js | \
   grep -o "http://.*\.war" | xargs curl -o webapps/openam.war

ADD run-openam.sh /tmp/run-openam.sh
RUN chmod +x /tmp/run-openam.sh

USER 1001

CMD ["/tmp/run-openam.sh"]
