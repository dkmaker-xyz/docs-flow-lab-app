# Test data: build the web app, serve it with nginx.
FROM node:24.11-alpine AS build
WORKDIR /app
COPY . .
RUN npm ci && npm run build

FROM nginx:1.29-alpine
COPY --from=build /app/dist /usr/share/nginx/html
