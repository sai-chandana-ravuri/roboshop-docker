FROM node:20
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install
#Here, mongodb is taken from image name, as because in docker it don't have dns host names.
ENV MONGO=true \
    MONGO_URL="mongodb://mongodb:27017/catalogue"    
CMD ["node", "server.js"]