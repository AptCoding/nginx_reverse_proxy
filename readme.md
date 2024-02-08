## Explanation:

### Docker Compose Configuration:
- Defines a Docker Compose service named `nginx`.
- Uses the latest version of the Nginx Docker image.
- Maps port 8000 on the host machine to port 8000 inside the Nginx container.
- Mounts the `nginx.conf` file from the host machine into the Nginx container in read-only mode.
- Connects the `nginx` service to a Docker bridge network named `nginx_network`.

### Nginx Configuration:
- Sets the maximum number of simultaneous connections to 1024.
- Defines an HTTP server block listening on port 8000.
- Responds to requests regardless of the domain name.
- Proxies incoming requests to the backend service running on `192.168.50.15:8080`.
- Sets the `Host`, `X-Real-IP`, `X-Forwarded-For`, and `X-Forwarded-Proto` headers to preserve client information.
- Returns a custom message "Welcome to the OCPP server" when the root URL is accessed directly.
