FROM nginxinc/openshift-nginx:stable

# users are not allowed to listen on priviliged ports
COPY default.conf /etc/nginx/conf.d/

EXPOSE 8080

COPY dist /usr/share/nginx/html
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]

