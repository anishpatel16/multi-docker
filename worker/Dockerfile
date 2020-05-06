FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
#instead of having startup command as dev, we should replace it with start. 
CMD ["npm", "run", "start"] 
