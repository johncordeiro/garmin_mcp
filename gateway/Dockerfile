FROM caddy:2-alpine
COPY Caddyfile /etc/caddy/Caddyfile
# Fail closed: refuse to start without a strong token
CMD ["sh", "-c", "[ ${#MCP_TOKEN} -ge 32 ] || { echo 'MCP_TOKEN ausente ou com menos de 32 caracteres' >&2; exit 1; }; exec caddy run --config /etc/caddy/Caddyfile --adapter caddyfile"]
