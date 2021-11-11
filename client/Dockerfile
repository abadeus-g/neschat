FROM node:14-alpine AS development 
#ENV NODE_ENV=production

WORKDIR /brain/client/src/app

COPY package*.json ./

RUN npm install 

RUN npm install -g @angular/cli

COPY . .

RUN npm run build

EXPOSE 4200
