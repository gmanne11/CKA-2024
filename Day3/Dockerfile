FROM node:18-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

RUN apk add --no-cache nginx

RUN rm -rf /usr/share/nginx/html/*

COPY .  /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
