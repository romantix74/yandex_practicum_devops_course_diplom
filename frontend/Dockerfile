# build
FROM node:16.20.2-alpine3.18 as builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
ENV NODE_ENV=development
ENV VUE_APP_API_URL=/
RUN npm run build


# release
FROM nginx:stable-alpine3.17-slim
ENV BACKEND baceknd:8081 
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/dist  /var/www-data

EXPOSE 80

