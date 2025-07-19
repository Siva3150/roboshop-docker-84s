FROM node:20 
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server 
COPY package.json .
COPY server.js . 
RUN npm install 
RUN chown -R roboshop:roboshop /opt/server
ENV MONGO="true" \
    REDIS_URL="redis://redis:6379" \
    MONGO_URL="mongodb://mongodb:27017/users"
USER roboshop
CMD ["node","server.js"]
