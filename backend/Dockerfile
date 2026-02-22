FROM node:20-alpine

WORKDIR /app

# Install dependencies first (better layer caching)
COPY package*.json ./
RUN npm ci --omit=dev

# Copy source code (node_modules and .env are excluded via .dockerignore)
COPY src ./src

EXPOSE 8080

CMD ["node", "src/index.js"]
