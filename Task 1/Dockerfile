# Using the official Node.js image as the base image
FROM node:18

# Setting the working directory inside the container
WORKDIR /app

# Copying package.json and package-lock.json to the working directory
COPY package*.json ./
RUN npm install 

# Copyting rest of the app code
COPY . .

# Specifying the port the app uses
EXPOSE 3000

# 6. Command to run app when container starts
CMD ["npm", "start"]
