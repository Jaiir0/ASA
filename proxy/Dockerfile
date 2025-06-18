FROM nginx:latest

RUN mkdir -p /etc/nginx/ssl

COPY default.conf /etc/nginx/conf.d/

# Copia a página personalizada
COPY index.html /usr/share/nginx/html/

COPY nginx-selfsigned.crt /etc/nginx/ssl/cert.crt
COPY nginx-selfsigned.key /etc/nginx/ssl/cert.key

# Ajusta permissões para segunraça da key
RUN chmod 644 /etc/nginx/ssl/cert.crt && \
    chmod 600 /etc/nginx/ssl/cert.key && \
    chown -R nginx:nginx /etc/nginx/ssl
