# nginx-reverse-proxy-demo

Test exercise based on the tutorial:
https://phoenixnap.com/kb/docker-nginx-reverse-proxy

# Instructions

1) Create CRTs and keys
    
    openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout proxy/ssl/example1.key -out proxy/ssl/example1.crt
    
    openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout proxy/ssl/example2.key -out proxy/ssl/example2.crt

2) Run in your terminal "docker-compose build"

3) Run in your terminal "docker-compose up -d"

4) Run in your terminal "docker-compose stop" to stop all containers

5) Run in your terminal "docker-compose down" to remove all resources
