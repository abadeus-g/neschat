# We specify node version and Image
# Name 'development' can be anything but have to be meaningful
FROM node:14-alpine AS development 

#Specify the working dir.
WORKDIR /brain/api/src/app

# Copy package*.json from host to container workdir
COPY package*.json ./

# We install package inside container
RUN npm install 

#Bundle App Source
COPY . .

RUN npm run build

EXPOSE 3000


################
## PRODUCTION###
################

FROM node:14-alpine AS production 
ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}

WORKDIR /brain/api/src/app

COPY --from=development /brain/api/src/app .

EXPOSE 3000

CMD ["node","dirst/main"]



