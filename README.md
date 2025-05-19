# nginx-reverse-proxy-demo

Test exercise based on the tutorial: <https://phoenixnap.com/kb/docker-nginx-reverse-proxy>.

This project deploy an `Nginx` instance with the `HTTPS` protocol and `self-signed certificates`. There are three `endpoints`: two `secured endpoints` and a `load-balancer endpoint`.

## Set up Docker cluster

1) Create directory ssl in proxy directory if it does not exist:

```bash
mkdir -p proxy/ssl
```

1) Create CRTs and keys, run in your terminal (Set default values):

```bash
openssl req \
  -x509 \
  -nodes \
  -days 365 \
  -newkey rsa:2048 \
  -keyout proxy/ssl/example1.key \
  -out proxy/ssl/example1.crt
```

```bash
openssl req \
  -x509 \
  -nodes \
  -days 365 \
  -newkey rsa:2048 \
  -keyout proxy/ssl/example2.key \
  -out proxy/ssl/example2.crt
```

2) Run in your terminal:

```bash
docker-compose build
```

3) Run in your terminal:

```bash
docker-compose up -d
```

4) Run in your terminal the following command to stop all containers:

```bash
docker-compose stop
```

5) Run in your terminal the following command to remove all resources:

```bash
docker-compose down
```

## How to try the application from localhost

Put in the browser when the cluster is running:

```text
http://localhost:8003/example1
```

or:

```text
http://localhost:8003/example2
```

## How to try the application from another machine in LAN network

1) Get the host IP in the LAN network with:

```text
hostname -I | awk '{print $1}'
```

it will return a similar output as `192.168.0.50`.

2) Put in the browser in another machine

```text
http://<host_ip>:8003/example1
```

or

```text
http://<host_ip>:8003/example2
```

Example: <http://192.168.0.50:8003/example1>
