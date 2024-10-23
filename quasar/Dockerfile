FROM node:21.7.3
# Create app directory
RUN mkdir -p /var/www/quasar:
WORKDIR /var/www/quasar
# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY ./quasar_vue/package*.json ./
RUN npm install
# If you are building your code for production
# RUN npm ci --only=production
# Bundle app source
COPY . .
EXPOSE 9000
CMD [ "npx", "quasar", "build" ]