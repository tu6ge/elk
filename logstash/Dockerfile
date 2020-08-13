FROM logstash:6.8.11

RUN logstash-plugin install logstash-filter-json

COPY ./nginx.conf /usr/share/logstash/pipeline/logstash.conf

# certs/keys for Beats and Lumberjack input
RUN mkdir -p /etc/pki/tls/{certs,private}
ADD ./logstash-beats.crt /etc/pki/tls/certs/logstash-beats.crt
ADD ./logstash-beats.key /etc/pki/tls/private/logstash-beats.key

# COPY ./logstash-filter-geoip-6.0.3-java.gem /home/

# RUN logstash-plugin install /home/logstash-filter-geoip-6.0.3-java.gem