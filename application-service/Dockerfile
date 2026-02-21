# Use an official Node.js runtime as a parent image
FROM node:18-alpine

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json first to leverage Docker cache
# if dependencies don't change
COPY package*.json ./

# Install app dependencies
RUN npm install

# Bundle app source
COPY . .

# Expose the port your Node.js app runs on (e.g., 3000, 8080)
# Assuming 3000 is a common port for Node.js apps
EXPOSE 3000

# Define the command to run your app
# Assuming your main script is index.js
CMD [ "node", "index.js" ]
