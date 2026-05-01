#build stage
FROM node:20 AS node-builder
RUN mkdir /build
WORKDIR /build
COPY package*.json ./
RUN npm ci
COPY . .

# production stage 
FROM alpine
RUN apk add --update nodejs
RUN addgroup -S node && adduser -S node -G node
USER node
RUN mkdir /home/node/code
WORKDIR /home/node/code
COPY --from=node-builder --chown=node:node /build .
CMD ["node", "index.js"]

# FROM alpine

# RUN apk add --update nodejs npm

# RUN addgroup -S node && adduser -S node -G node

# USER node

# RUN mkdir /home/node/code

# WORKDIR /home/node/code

# COPY --chown=node:node package*.json ./

# RUN npm ci

# COPY --chown=node:node . .

# CMD ["node", "index.js"] 

# =======================================================
# 1. Normal (ROOT) ======================================

# FROM node:20

# COPY index.js index.js

# CMD ["node", "index.js"]

# ========================================================
# 2. With user (node user) ==================================

# FROM node:20

# USER node

## COPY index.js /home/node/code/index.js ----------------
# COPY --chown=node:node index.js /home/node/code/index.js

# CMD ["node", "/home/node/code/index.js"]

# ========================================================
# 3. With WORKDIR ===========================================

# FROM node:20

# RUN useradd -ms /bin/bash okshan

# USER okshan

# WORKDIR /home/okshan/code

# COPY --chown=okshan:okshan index.js .

# CMD ["node", "index.js"]

# ========================================================
# 4. With custom user (okshan) =======================================

# FROM node:20

# USER node

# WORKDIR /home/node/code

# COPY --chown=node:node . .

# RUN npm ci

# CMD ["node", "index.js"]