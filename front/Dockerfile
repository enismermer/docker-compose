# Étape 1 : Build avec Node 20 (compatible Vite)
FROM node:20-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Construire le projet (Vite nécessite Node 20+)
RUN npm run build


# Étape 2 : Servir avec Nginx
FROM nginx:stable-alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
