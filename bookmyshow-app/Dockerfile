# Use Node 18
FROM node:18

WORKDIR /app

# Copy dependency files
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy app source
COPY . .

# Build the React app
ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm run build

# Install serve to run production build
RUN npm install -g serve

# Expose port
EXPOSE 3000

# Serve production build
CMD ["serve", "-s", "build", "-l", "3000"]
