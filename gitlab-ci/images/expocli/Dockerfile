FROM node:12.16.3-slim

# Ports of Expo Server
EXPOSE 19000-19006

# python & make for node-gyp
RUN apt-get update && \
    apt-get install -y procps \
    build-essential python 

# Up-to-date Node Package Manager
RUN npm install -g npm

# Update Yarn --force is used to avoid update issues
RUN npm install -g --force yarn

# Used to Run React-Native mobile App for Development
# --unsafe-perm bc we wanna maintain root user when executing
# npm command due to the behavior of node-gyp
RUN npm install -g expo-cli --unsafe-perm
