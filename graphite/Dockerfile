FROM graphiteapp/graphite-statsd:1.1.5-10
ADD storage-schemas.conf /opt/graphite/conf
ADD carbon.conf /opt/graphite/conf
RUN (ping -c 1 google.com && sed -i -e 's/v3\.8/v3.9/g' /etc/apk/repositories) || \
(printf 'http://repomirror-ict.eng.netapp.com/alpine-linux/v3.9/main\nhttp://repomirror-ict.eng.netapp.com/alpine-linux/v3.9/community' > /etc/apk/repositories) && apk update && apk upgrade
# Resolve a current nginx issue
RUN adduser -u 1000 -D -S -G www-data www-data
