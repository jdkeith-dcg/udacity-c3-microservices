# Set the base image and alias it
FROM beevelop/ionic AS ionic

# Create app directory
WORKDIR /usr/src/app

# Copy package.json, and package-lock.json
COPY package*.json ./

# Install all dependencies
RUN npm ci

# Copy everything else
COPY . .

# Bundle app source
RUN ionic build

# Run
FROM nginx:alpine

# COPY www
COPY --from=ionic /usr/src/app/www /usr/share/nginx/html
