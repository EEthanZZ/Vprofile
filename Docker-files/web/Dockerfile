FROM nginx
LABEL "project"="vprofile"

WORKDIR /etc/nginx/conf.d/
RUN rm -f default.conf
COPY nginvproapp.conf ./vproapp.conf