FROM node:21.7.3
# Create app directory
RUN mkdir -p /var/www/jam_api:
WORKDIR /var/www/jam_api
# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY ./jam_api/package*.json ./
RUN npm install
# If you are building your code for production
# RUN npm ci --only=production
# Bundle app source
COPY . .
EXPOSE 8080
CMD [ "node", "index.js" ]