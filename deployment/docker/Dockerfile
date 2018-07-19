#--------- Generic stuff all our Dockerfiles should start with so we get caching ------------
# Note this base image is based on debian
FROM kartoza/kbims_uwsgi:latest
MAINTAINER Dimas Ciputra<dimas@kartoza.com>

COPY REQUIREMENTS.txt /REQUIREMENTS.txt
RUN pip install -r /REQUIREMENTS.txt

ADD uwsgi.conf /home/web/uwsgi.conf
