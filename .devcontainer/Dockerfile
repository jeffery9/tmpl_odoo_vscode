FROM odoo:10.0
MAINTAINER geninIT <info@geninit.cn>

USER root

COPY ./pip.conf /root/.pip/pip.conf
COPY ./translate.py /usr/lib/python2.7/dist-packages/odoo/tools/
COPY ./odoo /usr/bin/odoo

RUN set -x; \
	sed -i 's/deb.debian.org/mirrors.163.com/g' /etc/apt/sources.list \
	&& sed -i 's/security.debian.org/mirrors.163.com/g' /etc/apt/sources.list 

RUN set -x; \   
    apt-get update && apt-get install -y  build-essential autoconf libtool freetds-bin freetds-dev python-dev libaio1 wget unzip

RUN set -x; \   
    pip install ptvsd

# RUN set -x;\
#     mkdir -p /opt/oracle \
#     && cd /opt/oracle \
#     && wget https://download.oracle.com/otn_software/linux/instantclient/195000/instantclient-basic-linux.x64-19.5.0.0.0dbru.zip \
#     && unzip instantclient-basic-linux.x64-19.5.0.0.0dbru.zip \
#     && sh -c "echo /opt/oracle/instantclient_19_5 > /etc/ld.so.conf.d/oracle-instantclient.conf" \
#     && mkdir -p /opt/oracle/instantclient_19_5/network/admin \
#     && ldconfig 

# ENV LD_LIBRARY_PATH /usr/local/lib:/usr/local/lib:/usr/lib:/usr/lib:/lib:/lib:/opt/oracle/instantclient_19_5

# Set default user when running the container
USER odoo

ENTRYPOINT ["/entrypoint.sh"]
CMD ["odoo"]
