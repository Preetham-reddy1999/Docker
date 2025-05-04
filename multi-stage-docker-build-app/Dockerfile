
# ---------- STAGE 1: Builder ----------
    FROM node:18 AS builder

    WORKDIR /app
    COPY package*.json ./
    RUN npm install
    COPY . .
    RUN npm run build
    
    
    # ---------- STAGE 2: Production ----------
    FROM node:18-slim AS production
    
    WORKDIR /app
    
    # Copy only built output and package files
    COPY --from=builder /app/dist ./dist
    COPY --from=builder /app/package*.json ./
    
    # Install only production dependencies
    RUN npm install --only=production
    
    # App uses dist/index.js via app.js
    CMD ["npm", "start"]
    