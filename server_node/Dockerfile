# Use a lightweight Node.js image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (if available) first
# This optimizes Docker build caching
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the server code (server.js, etc.)
COPY . .

# Render sets the PORT environment variable automatically (usually 10000).
# We expose it here for documentation, though Render ignores EXPOSE directives.

# Expose the port (Render expects 10000 usually, but you can set env vars)
ENV PORT=10000
EXPOSE 10000

# Start the server
CMD ["node", "server.js"]