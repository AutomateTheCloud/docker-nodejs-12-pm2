##-------------------------------------------------------------------------------------------------
# name:        nodejs-12-pm2
# description: Node.js 12 (with PM2)
# tag:         12.11.0
##-------------------------------------------------------------------------------------------------
FROM node:12.11.0-buster
MAINTAINER David Singer <david.singer@automatethe.cloud>

# Update Image
RUN apt-get update && \
    apt-get upgrade -y && \
    rm -rf /var/lib/apt/lists/*

# Install pm2
RUN npm install pm2 -g

# Update Kernel Parameters for Watcher Support
COPY resources/local.conf /etc/sysctl.d/local.conf

CMD ["pm2-runtime", "start", "pm2.json"]
