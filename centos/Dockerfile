FROM centos:latest
MAINTAINER Giuseppe Scrivano <gscrivan@redhat.com>

LABEL Name ostreetests
LABEL Release 1.0
LABEL Version 1.0

ADD atomic7-testing.repo /etc/yum.repos.d/
ADD run.sh /run.sh
ADD prepare.sh /prepare.sh

RUN yum install -y git redhat-rpm-config bison rsync yum-utils gcc git autoconf automake which gtk-doc libtool libcap-devel attr parallel make fuse-libs fuse-devel && yum-builddep -y ostree && \
    yum remove -y gjs && git clone https://github.com/GNOME/gnome-desktop-testing.git && /prepare.sh && yum clean all -y

CMD /run.sh
