# Nexus Docker Registry with Nginx

This setup runs a private Docker registry using Sonatype Nexus 3 behind an Nginx reverse proxy with SSL. It includes a `docker-compose.yml` file and an `nginx.conf`. SSL certificates should be placed in a `certs/` folder (not included here).

To run:
1. Generate self-signed certs with OpenSSL and place them in `certs/`.
2. Run `docker-compose up -d`.
3. Access the Nexus UI at `https://<your-ip>:443` (default admin password is inside the container at `/nexus-data/admin.password`).
4. Create a hosted Docker repo, then use `docker login`, `docker tag`, and `docker push` with your server IP and port 443.

This repo is meant for testing and learning purposes.
