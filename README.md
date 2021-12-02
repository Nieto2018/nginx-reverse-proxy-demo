# nginx-reverse-proxy-demo

Test exercise based on the tutorial:
https://phoenixnap.com/kb/docker-nginx-reverse-proxy

# Create CRT and key
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout example1.key -out example1.crt