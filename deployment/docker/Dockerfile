#--------- Generic stuff all our Dockerfiles should start with so we get caching ------------
# Note this base image is based on debian
FROM dimasciput/kartoza-django-bims:geonode
MAINTAINER Dimas Ciputra<dimas@kartoza.com>

COPY REQUIREMENTS.txt /REQUIREMENTS.txt
RUN pip install -r /REQUIREMENTS.txt
