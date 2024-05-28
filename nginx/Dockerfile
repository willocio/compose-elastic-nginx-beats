FROM nginx:stable

RUN rm -rf /var/log/nginx/access.log /var/log/nginx/error.log

RUN curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.17.21-amd64.deb && \
    dpkg -i filebeat-7.17.21-amd64.deb

COPY filebeat.yml /etc/filebeat/filebeat.yml
RUN chmod go-w /etc/filebeat/filebeat.yml
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT [ "/entrypoint.sh" ]