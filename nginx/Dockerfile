FROM nginx:alpine

MAINTAINER hong <ouranoshong@outlook.com>

COPY nginx.conf /etc/nginx/
COPY sites/*.conf /etc/nginx/sites-available/

ARG PHP_UPSTREAM=php-fpm

RUN adduser -D -H -u 1000 -s /bin/bash www-data \
    && rm /etc/nginx/conf.d/default.conf \
    && echo "upstream php-upstream { server ${PHP_UPSTREAM}:9000; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx"]

EXPOSE 80 443
