FROM node:20.20.2-alpine3.23 as builder
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install
#Here, mongodb is taken from image name, as because in docker it don't have dns host names.



FROM node:20.20.2-alpine3.23
WORKDIR /app
EXPOSE 8080
COPY --from=builder /app /app
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue" 
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN chown -R roboshop:roboshop /app
USER roboshop
#This is because, to start this as a service   
CMD ["server.js"]
ENTRYPOINT ["node"]           
# FROM node:20
# WORKDIR /app
# COPY package.json .
# COPY *.js .
# RUN npm install
# #Here, mongodb is taken from image name, as because in docker it don't have dns host names.
# ENV MONGO="true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"    
# CMD ["node", "server.js"]