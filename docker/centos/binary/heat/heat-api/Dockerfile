FROM %%KOLLA_NAMESPACE%%/%%KOLLA_PREFIX%%heat-base:%%KOLLA_TAG%%
MAINTAINER Kolla Project (https://launchpad.net/kolla)

# TODO: configure cfn and cloudwatch
# TODO: remove python-openstackclient once crux feature is added in start.sh
RUN yum -y install \
    openstack-heat-api \
    python-openstackclient \
    && yum clean all

COPY ./start.sh /start.sh
COPY ./check.sh /check.sh

COPY config-internal.sh config-external.sh /opt/kolla/

CMD ["/start.sh"]
