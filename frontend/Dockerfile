# Step 1: Use the official Node.js image to build the React app
FROM node:18-alpine as build

# Step 2: Set the working directory in the container
WORKDIR /app

# Step 3: Copy package.json and package-lock.json (or yarn.lock) to install dependencies
COPY package.json package-lock.json ./

# Step 4: Install dependencies
RUN npm install

# Step 5: Copy the rest of the application code into the container
COPY . .

# Step 6: Build the React app
RUN npm run build

# Step 7: Serve the React app using a simple server
FROM nginx:alpine

# Step 8: Copy the build directory from the first stage to the nginx server's html directory
COPY --from=build /app/build /usr/share/nginx/html

# Step 9: Expose port 8001 (default for nginx)
EXPOSE 8001

# Step 10: Run nginx server to serve the React app
CMD ["nginx", "-g", "daemon off;"]
