# Use an official Node.js runtime as the base image
FROM node:14-alpine

# Create a non-root user and switch to it
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app
USER node

# Set the working directory in the container
WORKDIR /home/node/app

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies
RUN npm install

COPY --chown=node:node . .

# Copy the rest of the application code to the container
COPY . /app

# Expose the port that the application listens on
EXPOSE 3000

# Define the command to run the application
CMD  node  index.js 
