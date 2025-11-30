FROM node:22-slim AS builder
WORKDIR /app
COPY ./package*.json .
RUN npm install
COPY ./client .
RUN npm run client-build

FROM nginx:alpine
COPY ./client/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]