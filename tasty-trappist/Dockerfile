#build stage
FROM node AS node-builder
WORKDIR /build
COPY package-lock.json package.json ./
RUN npm ci && npm run build
COPY ./dist .

# ngnx server stage
FROM nginx
COPY --from=node-builder /build /usr/share/nginx/html
