FROM python:3.11.9-alpine3.20

RUN apk add --no-cache ca-certificates tzdata tini curl jq build-base libffi-dev && \
    pip install --no-cache-dir parsedmarc && \
    pip install --no-cache-dir "msgraph-core<1.0.0" --force-reinstall && \
    apk del --no-cache build-base libffi-dev

COPY parsedmarc.ini /

## Set up geoipudate for automatic updates
# RUN wget https://github.com/maxmind/geoipupdate/releases/download/v6.0.0/geoipupdate_6.0.0_linux_amd64.tar.gz -O /tmp/geoipupdate.tar.gz
# RUN tar -zxf /tmp/geoipupdate.tar.gz --directory /tmp
# RUN cp /tmp/geoipupdate_6.0.0_linux_amd64/geoipupdate /usr/local/bin/
# COPY GeoIP.conf /usr/local/etc/
# RUN geoipupdate
# RUN rm -rf /tmp/geoipupdate_6.0.0_linux_amd64/
# RUN rm /tmp/geoipupdate.tar.gz

# COPY geoip_update_cron /etc/cron.d/
# RUN chmod 644 /etc/cron.d/geoip_update_cron

