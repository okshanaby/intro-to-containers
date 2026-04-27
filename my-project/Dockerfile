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

FROM node:20

RUN useradd -ms /bin/bash okshan

USER okshan

WORKDIR /home/okshan/code

COPY --chown=okshan:okshan index.js .

CMD ["node", "index.js"]