# Elastic stack (ELK) on Docker

It is a clone of the following repository - https://github.com/deviantony/docker-elk, done for some testing purposes.

## The initial changes
1. Raplace the images for Docker Hub official ones, due to some issue accessing images in Elastic repo via HTTP proxy (related to redirection to IP address, whereas IP whitelisting was not implemented in Proxy configuration).
1. Change ELK ver. to 8.6.0
1. Remove most of the extensions, leave just Filebeat (though not sure if it will be used either).
1. Change ports mapping for Elasticsearch and Kibana (9200 -> 9220, 9300 -> 9330, 5601 -> 5661).
1. Make Kibana available just on a localhost IP address, as it will be accessed via reverse proxy.
