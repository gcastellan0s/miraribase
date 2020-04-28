# Stage 1 - build frontend app
FROM node:10-alpine as build-deps

WORKDIR /app/

COPY frontend/package.json frontend/package-lock.json /app/
RUN npm install

COPY frontend /app/
COPY .envs /app/.envs
RUN npm run build

FROM nginx:alpine

COPY nginx/production.conf /etc/nginx/nginx.conf
COPY --from=build-deps /app/dist/ /dist/

CMD ["nginx", "-g", "daemon off;"]
