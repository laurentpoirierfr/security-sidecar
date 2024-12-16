FROM openresty/openresty:alpine-fat

RUN apk update && apk add --no-cache libintl openssl-dev git gcc

RUN luarocks install lua-resty-openidc

COPY *.template /etc/nginx/templates/

CMD envsubst < /etc/nginx/templates/default.conf.template > /etc/nginx/conf.d/default.conf \ 
    && /usr/local/openresty/nginx/sbin/nginx -g "daemon off;"

