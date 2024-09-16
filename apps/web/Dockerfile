FROM node:18-alpine

WORKDIR /app

COPY package.json package-lock.json ./

ARG ENV=production
ENV ENV=${ENV}

RUN npm ci

COPY . .

RUN if [ "$ENV" = "production" ]; then \
    npm run build; \
    fi

EXPOSE 3000

CMD if [ "$ENV" = "production" ]; then \
    npm start; \
    else \
    npm run dev; \
    fi