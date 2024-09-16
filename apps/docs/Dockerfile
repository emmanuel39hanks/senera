FROM node:18-alpine

WORKDIR /app
COPY package*.json ./

ARG ENV=production
ENV ENV=${ENV}

RUN if [ "$ENV" = "production" ]; then \
    npm ci; \
    else \
    npm install; \
    fi

COPY . .

RUN if [ "$ENV" = "production" ]; then \
    npm run build; \
    fi

CMD if [ "$ENV" = "production" ]; then \
    npm run serve -- --port 3001; \
    else \
    npm run start -- --port 3001; \
    fi