# security-sidecar

Exemple de mise en place de sécurité d'accès web via nginx.


## References

### basic auth

* none

### oidc 

* https://github.com/zmartzone/lua-resty-openidc
* https://kevalnagda.github.io/configure-nginx-and-keycloak-to-enable-sso-for-proxied-applications
* https://github.com/jirutka/nginx-oidc-njs
* https://github.com/nginx-openid-connect/nginx-oidc-ping-identity
* https://github.com/nginxinc/nginx-openid-connect
* https://docs.nginx.com/nginx/deployment-guides/single-sign-on/ping-identity/
* https://www.f5.com/company/blog/nginx/validating-oauth-2-0-access-tokens-nginx


je dois livrer des applications front web ainsi :

Sur les routes NON sécurisées suivantes :

- "/"    : accès public   : /usr/share/nginx/html;
- "/ops" : proxy sur      : http://${FORWARD_HOST}:${FORWARD_PORT}/ops;

Sur les routes sécurisées suivantes :

- "/ui"  : accès sécurisé : /usr/share/nginx/html/ui; 
- "/api" : proxy sur      : http://${FORWARD_HOST}:${FORWARD_PORT}/api;