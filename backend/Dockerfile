FROM node:20
# Expose 8080 port so that this container will be listened on 8080 port by any other containers
EXPOSE 8080
#Before this In Expense backend project we created backend.service to configure DB_HOST details.. we directly configure now
ENV DB_HOST=mysql
RUN useradd expense
#Create a directory /opt/server.. we can use any directory we want similar to /app we used before
RUN /opt/server
#Move to /opt/server directory
WORKDIR /opt/server
#Make expense user as owner of created directory
RUN chown expense:expense -R /opt/server
#copy all the js files into current working directory i.e., /opt/server which we can refer by dot(.)
COPY *.js .
RUN npm install
#Before this In Expense backend project we created backend.service to configure which js file to run on start of backend service.. we directly configure now
#Load and run index.js during container creation --> docker run command
CMD [ "node","index.js" ]



