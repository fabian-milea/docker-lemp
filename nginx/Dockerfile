FROM nginx:alpine

COPY nginx.conf /etc/nginx
COPY symfony.conf /etc/nginx/sites.available

RUN mkdir -p /etc/nginx/sites-enabled/ \
    && ln -s /etc/nginx/sites-available/symfony.conf /etc/nginx/sites-enabled/symfony.conf \
    && rm /etc/nginx/conf.d/default.conf

RUN echo "upstream php-upstram { server php:9001; }" > /etc/nginx/conf.d/upstream.conf

RUN adduser -D -g '' -G www-data www-data

CMD ["nginx"]

EXPOSE 90
EXPOSE 443