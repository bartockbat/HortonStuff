FROM registry-rhconnect.rhcloud.com/rhel71_updates
MAINTAINER SequenceIQ

#Install necessary tools
RUN yum -y groupinstall "Development Tools"
RUN yum -y install java-1.7.0-openjdk
RUN yum -y update

RUN curl -Ls https://raw.githubusercontent.com/sequenceiq/ambari-shell/master/latest-snap.sh | bash
ADD install-cluster.sh /tmp/
ADD wait-for-host-number.sh /tmp/
WORKDIR /tmp

ENTRYPOINT ["java", "-jar", "ambari-shell.jar"]
