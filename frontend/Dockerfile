# build
# 20.11.1 и другие более новых не собирается с ошибкой парсинга сайта vue или openssl, 
#  обратится к разработчикам
FROM node:16.20.2-alpine3.18 as builder
WORKDIR /usr/src/app
COPY . .
RUN npm install
RUN npm run build


FROM nginx:stable-alpine3.17-slim
WORKDIR /app
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /usr/src/app/dist/ /var/www-data/
EXPOSE 80


