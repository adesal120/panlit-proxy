# Railway Caddy Proxy for Panlit Custom Domains
FROM caddy:2-alpine

# Copy the Caddyfile
COPY Caddyfile /etc/caddy/Caddyfile

# Caddy data directory for certificates
VOLUME /data
VOLUME /config

# Expose HTTP and HTTPS ports
EXPOSE 80 443

# Run Caddy
CMD ["caddy", "run", "--config", "/etc/caddy/Caddyfile", "--adapter", "caddyfile"]
