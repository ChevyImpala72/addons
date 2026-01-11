ARG BUILD_FROM
FROM ${BUILD_FROM}

# Install nginx for serving the web UI
RUN apk add --no-cache \
    nginx \
    curl

# Copy root filesystem
COPY rootfs /

# Set up nginx
RUN mkdir -p /run/nginx

# Health check
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
    CMD curl --fail http://127.0.0.1:8099/health || exit 1
