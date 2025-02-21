# Use a base image with HAProxy and Keepalived support
FROM alpine:latest

# Install HAProxy and Keepalived
RUN apk update && \
    apk add --no-cache haproxy keepalived systemd systemd-openrc

# Copy HAProxy and Keepalived configuration files
COPY haproxy.cfg /etc/haproxy/haproxy.cfg
COPY keepalived.conf /etc/keepalived/keepalived.conf

# Expose necessary ports
EXPOSE 8080

# Start both Keepalived and HAProxy
CMD /usr/sbin/keepalived -D && /usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg
