FROM nginx:1.19.0-alpine

RUN apk update && apk add apache2-utils libintl

COPY *.template /etc/nginx/templates/

CMD htpasswd -Bbn "$BASIC_AUTH_USERNAME" "$BASIC_AUTH_PASSWORD" > /etc/nginx/auth.htpasswd \
    && envsubst < /etc/nginx/templates/default.conf.template > /etc/nginx/conf.d/default.conf \
    && nginx -g "daemon off;"

