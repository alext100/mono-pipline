# ---- Build + Run in one image ----
FROM node:18-alpine

WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install all dependencies (including dev for building)
RUN npm install --frozen-lockfile

# Copy the rest of the source code
COPY . .

# Build the NestJS app
RUN npm run build

# Expose port
EXPOSE 10000

# Run production
CMD ["node", "dist/main.js"]
