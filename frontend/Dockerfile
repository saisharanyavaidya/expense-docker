FROM nginx
#Remove default index.html file
RUN rm -rf /usr/share/nginx/html/index.html
#Removing default configuration files provided by nginx at two places
RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
RUN mkdir -p /var/cache/nginx/client_temp && \
        mkdir -p /var/cache/nginx/proxy_temp && \
        mkdir -p /var/cache/nginx/fastcgi_temp && \
        mkdir -p /var/cache/nginx/uwsgi_temp && \
        mkdir -p /var/cache/nginx/scgi_temp && \
        chown -R nginx:nginx /var/cache/nginx && \
        chown -R nginx:nginx /etc/nginx/ && \
        chmod -R 755 /etc/nginx/ && \
        chown -R nginx:nginx /var/log/nginx
RUN touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid
#Copy expense.conf in default config folder so that this will be referred 
#Here nginx is built on debian so default path is /etc/nginx/nginx.conf instead of actual path we gave in expenses documentation /etc/nginx/default.d/expense.conf
COPY expense.conf /etc/nginx/nginx.conf
COPY code /usr/share/nginx/html/
#till above code, root user access will be there.. now nginx user access will be there
USER nginx
