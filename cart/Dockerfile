FROM node:20
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install
#Here, mongodb is taken from image name, as because in docker it don't have dns host names.
ENV REDIS_HOST="redis" \
    CATALOGUE_HOST="catalogue" \
    CATALOGUE_PORT="8080"   
CMD ["node", "server.js"]