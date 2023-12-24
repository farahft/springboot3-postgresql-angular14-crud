# stage 1 : build angular app
FROM node:20.10.0-alpine3.19 as build-step

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build --prod

# stage 2 : run npx http-server
FROM node:20.10.0-alpine3.19

WORKDIR /app

COPY --from=build-step /app/dist/angular-mean-crud-tutorial /app

RUN npm install -g http-server

EXPOSE 9999

CMD ["http-server", "-p", "9999", "-c-1", "/app"]