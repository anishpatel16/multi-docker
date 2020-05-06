#Nothin change except for startup command insteaad of dev, have start.  npm run start
FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "start"]