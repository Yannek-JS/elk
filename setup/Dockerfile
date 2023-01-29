ARG ELASTIC_VERSION

# You can use either the image from Docker Hub or directly from Elastic

# https://www.docker.elastic.co/
#FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION}

# Docker Hub image
FROM elasticsearch:${ELASTIC_VERSION}

USER root

RUN set -eux; \
	mkdir /state; \
	chmod 0775 /state; \
	chown elasticsearch:root /state

USER elasticsearch:root

ENTRYPOINT ["/entrypoint.sh"]
