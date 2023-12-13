# Use a base image with Node.js
FROM node:14

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the application code
COPY . /usr/src/app/

# Expose port 80
EXPOSE 80

# Start the application
CMD ["node", "app.js"]
