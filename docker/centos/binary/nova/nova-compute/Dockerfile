FROM %%KOLLA_NAMESPACE%%/%%KOLLA_PREFIX%%nova-base:%%KOLLA_TAG%%
MAINTAINER Kolla Project (https://launchpad.net/kolla)

RUN yum -y install openstack-nova-compute \
        openvswitch \
        sysfsutils && yum clean all

COPY config-nova-compute.sh /opt/kolla/config-nova-compute.sh

COPY ./start.sh /start.sh

COPY config-internal.sh config-external.sh /opt/kolla/

VOLUME [ "/sys/fs/cgroup" ]

CMD ["/start.sh"]
