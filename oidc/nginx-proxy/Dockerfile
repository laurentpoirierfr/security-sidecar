FROM nginx:1.19.0-alpine

RUN apk update && apk add libintl

COPY *.template /etc/nginx/templates/

CMD envsubst < /etc/nginx/templates/default.conf.template > /etc/nginx/conf.d/default.conf && nginx -g "daemon off;"

