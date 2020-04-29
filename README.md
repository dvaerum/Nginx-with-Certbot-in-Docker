# Nginx with Certbot in Docker
This docker container is based on the last LTS of Ubuntu server. It is make as a service for handling the creation, renewal and removed of TLS certificates simply by listing the domains. It also setup Nginx and allow you to use it as a web-server or a reverse proxy.

## Optional configuration variables
### DOMANIS
List the domains that you need a certificate to. If you have more then one domain you can seperate them with a comma (,) as showen in the example.
```
DOMAINS=example.com,www.example.com
```

### TEST
Set the variable to anything to enabled the used of LetsEncrypt's stating/testing environment.
https://letsencrypt.org/docs/staging-environment/
```
TEST=1
```

### NGINX_LOG_ACCESS
```
NGINX_LOG_ACCESS=N
```

### NGINX_LOG_ERROR
```
NGINX_LOG_ERROR=Y
```

### X_FRAME_OPTIONS
If not configured DENY is the default
```
X_FRAME_OPTIONS=SAMEORIGIN
```

## Mounting Point
### /etc/nginx/sites-available
```
./sites-available:/etc/nginx/sites-available:ro
```

### /etc/letsencrypt
```
./letsencrypt:/etc/letsencrypt
```
