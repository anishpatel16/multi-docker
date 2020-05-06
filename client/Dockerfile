FROM node:alpine as builder
WORKDIR '/app'
#copy package.json file to working dir
COPY ./package.json ./  
RUN npm install
#copy everything else
COPY . . 
#build prod version of build . 
RUN npm run build
#output of this will be folder called build where all prod files store in the app folder workdir we created

#we created nginx extra since before it was only listening on port 80 but now we expose to port 8000
FROM nginx
EXPOSE 3000
#copy nginx default.conf file and copy and override previous file of default.conf 
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html

