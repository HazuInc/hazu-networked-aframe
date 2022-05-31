# Use the official lightweight Node.js 12 image.
# https://hub.docker.com/_/node
FROM node:17-slim

# Create and change to the app directory.
WORKDIR /usr/src/app
# RUN ls -la /usr/src/app

# Copy application dependency manifests to the container image.
# A wildcard is used to ensure both package.json AND package-lock.json are copied.
# Copying this separately prevents re-running npm install on every code change.
COPY package*.json ./
COPY webpack*.js ./
COPY ./src ./src
# RUN ls -la /usr/src/app
# RUN ls -la /usr/src/app/src

# Install dependencies.
# If you add a package-lock.json speed your build by switching to 'npm ci'.
RUN npm ci --quiet --legacy-peer-deps

# Copy local code to the container image.
COPY . ./
RUN ls -la /usr/src/app

# Run the web service on container startup.
CMD ["npm", "start"]
