# Stage 1: Use the official Node.js Alpine image as the base image
FROM node:21.7.3

# Set the working directory inside the container
RUN mkdir -p /var/www/quasar:
WORKDIR /var/www/quasar

# Copy necessary files for dependency installation
COPY ./quasar_vue/* ./
COPY ./quasar_vue/src/ ./src/
COPY ./quasar_vue/public/ ./public/

# Install dependences
RUN rm -rf node_modules package-lock.json

# Install dependencies
RUN npm install

# Build the Quasar app for production
RUN npx quasar build

# Copy the rest of the application source code
COPY . .

# Install a web server to serve the built files
RUN npm install -g serve

# Expose the port that the app will run on
EXPOSE 3000

# Command to run the application
CMD ["serve", "-s", "dist/spa"]