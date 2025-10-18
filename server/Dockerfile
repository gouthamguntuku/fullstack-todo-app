# Use Node.js 18 Alpine as the base image (lightweight Linux distribution)
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install application dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Expose port 5000 to the host machine
EXPOSE 5000

# Command to run the application
CMD ["node", "server.js"]
