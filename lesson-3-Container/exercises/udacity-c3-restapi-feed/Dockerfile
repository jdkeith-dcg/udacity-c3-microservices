# Set the base image
FROM node:12

# Create app directory
WORKDIR /usr/src/app

# Copy package.json, and package-lock.json
COPY package*.json ./

# Install all dependencies
RUN npm ci

# Copy everything else
COPY . .

# Expose the port
EXPOSE 8080

# Define the command to be executed
CMD [ "npm", "run", "dev" ]
