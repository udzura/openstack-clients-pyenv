FROM centos:6.6
MAINTAINER Uchio Kondo <udzura@udzura.jp>

USER root
RUN rpm -Ui http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
RUN yum -y groupinstall "Development Tools"
RUN yum -y install git
RUN git clone https://github.com/yyuu/pyenv.git /usr/local/pyenv
RUN echo 'export PYENV_ROOT="/usr/local/pyenv"' >> /etc/profile.d/pyenv.sh
RUN echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> /etc/profile.d/pyenv.sh
RUN echo 'eval "$(pyenv init -)"' >> /etc/profile.d/pyenv.sh

RUN yum -y install tar zlib-devel readline-devel bzip2-devel sqlite-devel openssl-devel
RUN ( source /etc/profile.d/pyenv.sh; pyenv install 2.7.11 )
RUN ( source /etc/profile.d/pyenv.sh; pyenv global 2.7.11 )
RUN ( source /etc/profile.d/pyenv.sh; \
      pip install python-openstackclient python-neutronclient python-novaclient; \
      pyenv rehash )

RUN ( cd /usr/local/pyenv/versions/2.7.11 ; tar czf /tmp/python-2.7.11-with-openstack-clients.tar.gz ./ )

CMD ["cp", "/tmp/python-2.7.11-with-openstack-clients.tar.gz", "/pkg/python-2.7.11-with-openstack-clients.tar.gz"]
