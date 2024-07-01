#node js version 20 from alpine OS
FROM node:20.15.0-alpine3.20 
# Expose 8080 port so that this container will be listened on 8080 port by any other containers
EXPOSE 8080
#Before this In Expense backend project we created backend.service to configure DB_HOST details.. we directly configure now(mysql is container name of DB)
ENV DB_HOST=mysql
#Create a directory /opt/server.. we can use any directory we want similar to /app we used before
#Move to /opt/server directory
#Make expense user as owner of created directory
RUN addgroup -S expense && adduser -S expense -G expense \
    && mkdir /opt/server \
    && chown expense:expense -R /opt/server 
WORKDIR /opt/server
#copy package.json to present working dir so that we can install required dependencies here we do npm install in below RUN instruction
COPY package.json .
#copy all the js files into current working directory i.e., /opt/server which we can refer by dot(.)
COPY *.js /opt/server/
RUN npm install
#this means backend should run with expense user and not with root user
USER expense
#Before this In Expense backend project we created backend.service to configure which js file to run on start of backend service.. we directly configure now
#Load and run index.js during container creation --> docker run command
CMD [ "node","index.js" ]



