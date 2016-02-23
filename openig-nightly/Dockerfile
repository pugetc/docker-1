FROM tomcat:8-jre8

ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
ENV JAVA_OPTS -Dopenig.base=/root/config
WORKDIR $CATALINA_HOME

EXPOSE 8080

# download OpenIG nightly WAR
RUN curl -o webapps/ROOT.war http://maven.forgerock.org/repo/repo/org/forgerock/openig/openig-war/5.0.0-SNAPSHOT/openig-war-5.0.0-SNAPSHOT.war

ADD run-openig.sh /tmp/run-openig.sh

CMD ["/tmp/run-openig.sh"]
