FROM node:lts-alpine

RUN apk add --no-cache nginx

ENV VITE_API_URL=/api \
    APP_DIR=/app \
    NGINX_HTML=/usr/share/nginx/html

WORKDIR ${APP_DIR}

#COPY .  .

COPY nginx.conf /etc/nginx/http.d/default.conf

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

EXPOSE 80

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
CMD ["serve"]
