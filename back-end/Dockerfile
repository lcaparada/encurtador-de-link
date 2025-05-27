FROM node:20

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

RUN apt-get update && apt-get install -y curl \
  && curl -o /usr/local/bin/wait-for-it https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh \
  && chmod +x /usr/local/bin/wait-for-it

COPY . .

COPY .env ./

RUN npm run build

EXPOSE 3001

CMD ["npm", "run", "start:prod"]