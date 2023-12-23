# First Stage: Build the Angular app
FROM node:16.13.1-alpine AS build
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm ci
COPY . .
CMD ["npm", "run", "build"]

# Second Stage: Create a smaller image for production
FROM node:16.13.1-alpine
WORKDIR /usr/src/app
COPY --from=build /usr/src/app/dist ./dist
EXPOSE 7000
CMD ["npx", "http-server", "./dist"]


