#Notice how we don't have docker volumes in this production build (don't need it)
FROM node:alpine 
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

#to specify a second build phase, just use "FROM" 
FROM nginx
#copy items from build folder crated from 1st phase (indicated as '0') to below path
COPY --from=0 /app/build /usr/share/nginx/html