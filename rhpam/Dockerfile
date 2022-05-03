FROM registry.redhat.io/rhpam-7/rhpam-kieserver-rhel8:7.12.1-3

ADD --chown=jboss:root ./contrib/application-users.properties /opt/eap/standalone/configuration/application-users.properties
ADD --chown=jboss:root ./contrib/application-roles.properties /opt/eap/standalone/configuration/application-roles.properties
ADD --chown=jboss:root ./contrib/kafka-serializer-1.0.jar  /opt/eap/standalone/deployments/ROOT.war/WEB-INF/lib/kafka-serializer-1.0.jar
ADD --chown=jboss:root ./contrib/kafka-workitem-7.52.0.Final-redhat-00007.jar /opt/eap/standalone/deployments/ROOT.war/WEB-INF/lib/kafka-workitem-7.52.0.Final-redhat-00007.jar
ADD --chown=jboss:root ./contrib/repository/ /home/jboss/.m2/repository/

ENV KIE_SERVER_CONTAINER_DEPLOYMENT=vcoo_1.0.0=com.poc:vcoo:1.0.0

USER root
RUN chmod 664 /opt/eap/standalone/configuration/application-users.properties && \
    chmod 664 /opt/eap/standalone/configuration/application-roles.properties && \
    chown -R jboss:root /home/jboss/.m2/repository/*
USER jboss