FROM nginx
#Remove default index.html file
RUN rm -rf /usr/share/nginx/html/index.html
#Removing default configuration files provided by nginx at two places
RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
COPY expense.conf /etc/nginx/nginx.conf
COPY code /usr/share/nginx/html/
