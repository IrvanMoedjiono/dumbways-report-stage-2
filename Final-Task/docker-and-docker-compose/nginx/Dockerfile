FROM nginx:latest
COPY monitoring.conf /etc/nginx/conf.d/
COPY prometheus.conf /etc/nginx/conf.d/
COPY cicd.conf /etc/nginx/conf.d/
COPY frontend.conf /etc/nginx/conf.d/
COPY backend.conf /etc/nginx/conf.d/
COPY .htpasswd /etc/nginx/
