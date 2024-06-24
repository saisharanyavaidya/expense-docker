FROM nginx
#Remove default index.html file
RUN rm -rf /usr/share/nginx/html/index.html
#Removing default configuration files provided by nginx at two places
RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
#Copy expense.conf in default config folder so that this will be referred 
#Here nginx is built on debian so default path is /etc/nginx/nginx.conf instead of actual path we gave in expenses documentation /etc/nginx/default.d/expense.conf
COPY expense.conf /etc/nginx/nginx.conf
COPY code /usr/share/nginx/html/
