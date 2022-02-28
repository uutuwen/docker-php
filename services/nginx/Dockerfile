ARG NGINX_IMAGE_TAG

FROM nginx:${NGINX_IMAGE_TAG}

RUN set -x ; \
    addgroup -g 82 -S www-data ; \
    adduser -u 82 -D -S -G www-data www-data && exit 0 ; exit 1

WORKDIR "/code"
