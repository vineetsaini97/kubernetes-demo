FROM node:20

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the port your app listens on
EXPOSE 3500

# Start the app
CMD ["node", "server.js"]

