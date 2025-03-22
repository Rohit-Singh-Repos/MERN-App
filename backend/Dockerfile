# Step 1: Use the Node.js image as the base image
FROM node:19

# Set the working directory for the backend
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if available)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the server code
COPY . .

# Expose the backend port
EXPOSE 5000

# Start the Node.js server
CMD ["npm","run", "server"]

