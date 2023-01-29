ARG ELASTIC_VERSION

# You can use either the image from Docker Hub or directly from Elastic

# https://www.docker.elastic.co/
#FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION}

# docker hub image
FROM elasticsearch:${ELASTIC_VERSION}

# The lines below help solve the issue on different privileges to volume content 
# between the docker container (inside it) and the host. 
# You need to have the same UID and GID for elasticsearch user in both those places.
# By default, elasticsearch user has got 1000:1000 UID:GID in the container.
# The below lines change it from 1000:1000 to 2000:2000. You may adjust it to your needs.
USER root
RUN usermod --uid 2000 elasticsearch &&\
    groupmod --gid 2000 elasticsearch &&\
    find / \( -path /proc -o -path /var/cache -o -path /etc/ssl/private -o -path /root \) -prune -o -user 1000 -exec chown elasticsearch '{}' \;
USER elasticsearch:root

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
