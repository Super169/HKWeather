FROM node:carbon-slim

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package.json .
# For npm@5 or later, copy package-lock.json as well
# COPY package.json package-lock.json ./

# There will have warning in building docker image:
# nomnom@1.5.2: Package no longer supported 
# But it will cause the image file if adding -g artillery --unsafe-perm=true --allow-root 
# as suggested in https://github.com/artilleryio/artillery/issues/671
# RUN npm install -g artillery --unsafe-perm=true --allow-root
# So, just ignore the warning at this moment until a fix is provided later
RUN npm install 
# If you are building your code for production
# RUN npm install --only=production

# Bundle app source
COPY . .

EXPOSE 8080
CMD [ "npm", "start" ]