FROM %%KOLLA_NAMESPACE%%/%%KOLLA_PREFIX%%neutron-base:%%KOLLA_TAG%%
MAINTAINER Kolla Project (https://launchpad.net/kolla)

# Install required packages
RUN yum install -y ebtables && yum clean all

COPY check.sh start.sh /

COPY config-internal.sh config-external.sh /opt/kolla/

CMD ["/start.sh"]
