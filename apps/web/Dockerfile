# Test data: build the web app, serve it with nginx.
FROM node:24.11-alpine AS build
WORKDIR /app
COPY . .
RUN npm ci && npm run build

FROM python:3.13-slim
COPY --from=build /app/dist /usr/share/nginx/html
