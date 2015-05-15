FROM registry.access.redhat.com/rhel 

#If you are on a non-RHEL host, use the below base image
#FROM registry-rhconnect.rhcloud.com/rhel71_updates

MAINTAINER SequenceIQ

ENV VERSION 0.5.3

#Install necessary tools
RUN yum -y groupinstall "Development Tools"
RUN yum -y install java-1.7.0-openjdk
RUN yum -y update

# install the periscope app
ADD https://s3-eu-west-1.amazonaws.com/maven.sequenceiq.com/releases/com/sequenceiq/periscope/$VERSION/periscope-$VERSION.jar /periscope.jar


# extract schema files
RUN unzip periscope.jar schema/* -d /

ADD bootstrap /tmp

ENTRYPOINT ["/tmp/start_periscope.sh"]
