# This is a basic Dockerfile for a Node.js application

# Use the official Node.js image as a base
From node:18

# set the working directory for the application inside container
WORKDIR /app

# Copy the package.json and package-lock.json files to the working directory
COPY package*.json ./
RUN npm install

# copy source code to the working directory
COPY . .

# Expose the port the app runs on
EXPOSE 3000

# START THE APPLICATION
CMD ["npm", "start"]