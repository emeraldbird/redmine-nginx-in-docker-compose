FROM nginx:alpine
COPY ./nginx.conf /etc/nginx/nginx.conf
RUN apk update && \
    apk add openssl && \
    mkdir -p /etc/nginx/certs && \
    cd /etc/nginx/certs/ && \
    openssl req -x509 \
            -sha256 \
            -days 3560 \
            -nodes \
            -newkey rsa:4096 \
            -subj '/C=US' \
            -keyout redmine.key -out redmine.crt
ENTRYPOINT ["nginx", "-g", "daemon off;"]

