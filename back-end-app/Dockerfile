# ---- Builder ----
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install --frozen-lockfile
COPY . .
RUN npm run build

# ---- Production ----
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --only=production --frozen-lockfile
COPY --from=builder /app/dist ./dist

EXPOSE 10000
CMD ["node", "main.js"]
