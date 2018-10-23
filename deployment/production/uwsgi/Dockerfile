#--------- Generic stuff all our Dockerfiles should start with so we get caching ------------
# Note this base image is based on debian
ARG BIMS_TAG=stable
FROM kartoza/kbims_uwsgi:${BIMS_TAG}
MAINTAINER Dimas Ciputra<dimas@kartoza.com>

COPY REQUIREMENTS.txt /REQUIREMENTS.txt
RUN pip install -r /REQUIREMENTS.txt

ARG LEDET_TAG=develop
WORKDIR /usr/src
RUN git clone --depth=1 --branch ${LEDET_TAG} git://github.com/kartoza/LEDET_BIMS.git /usr/src/LEDET_BIMS
RUN cd /usr/src/LEDET_BIMS/django_project && git submodule init && git submodule update
RUN mkdir -p /usr/src/ledet
RUN cp -r LEDET_BIMS/django_project/* /usr/src/ledet

WORKDIR /usr/src/ledet

ADD uwsgi.conf /usr/src/ledet/uwsgi.conf

CMD ["uwsgi", "--ini", "/usr/src/ledet/uwsgi.conf"]
