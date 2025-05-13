Nexus Docker Registry with Nginx Reverse Proxy

This repository provides configuration files to set up a private Docker registry using [Sonatype Nexus 3] behind an Nginx reverse proxy with SSL support.

What's Included

docker-compose.yml: Defines Nexus and Nginx containers

nginx.conf: Nginx reverse proxy configuration for HTTPS and registry routing


> Note: The certs/ directory (used to store SSL certificate and key) is not included in this repo because it contains private self-signed certificates. You can generate your own.

1. Generate SSL Certificates

Use OpenSSL to create a self-signed certificate and place the files in a certs/ folder at the project root:

mkdir certs
openssl req -x509 -newkey rsa:2048 -nodes -keyout certs/cert.key -out certs/cert.crt -days 365


2. Start the Stack

docker-compose up -d


3. Access Nexus UI

Visit: https://<your-ip>:443
Default user: admin
Password: inside the container at /nexus-data/admin.password
---

Notes

Ensure your Docker daemon allows self-signed certificates or configure insecure-registries if needed.

For push/pull operations, you'll need to login via:

docker login <your-ip>:443



---
