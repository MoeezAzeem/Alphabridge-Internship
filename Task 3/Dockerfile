# Base image
FROM node:18

# Create app directory
WORKDIR /app

# Copy both backend and frontend package.json files
COPY backend/package*.json ./backend/
COPY frontend/package*.json ./frontend/

# Install dependencies for backend and frontend
WORKDIR /app/backend
RUN npm install

WORKDIR /app/frontend
RUN npm install

# Copy the full source code
COPY . .

# Set environment variable for React live reload
ENV CHOKIDAR_USEPOLLING=true

# Install concurrently to run both servers
WORKDIR /app
RUN npm install -g concurrently

# Expose ports
EXPOSE 3000
EXPOSE 5000

# Start both servers
CMD concurrently "cd backend && npx nodemon index.js" "cd frontend && npm start"
