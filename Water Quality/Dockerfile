# Gunakan image Node.js yang ringan
FROM node:18-slim

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependensi
RUN npm install --production

# Copy seluruh source code
COPY . .

# Environment variables
ENV PORT=8080
ENV NODE_ENV=production

# Expose port
EXPOSE 8080

# Jalankan aplikasi
CMD ["node", "js/server.js"]
