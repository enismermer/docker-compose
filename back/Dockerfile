# Étape 1 : Utiliser une image Node officielle
FROM node:18-alpine

# Étape 2 : Créer un répertoire de travail dans le conteneur
WORKDIR /app

# Étape 3 : Copier les fichiers de configuration
COPY package*.json ./

# Étape 4 : Installer les dépendances
RUN npm install

# Étape 5 : Copier le reste du code
COPY . .

# Étape 6 : Générer le client Prisma (nécessaire après npm install)
RUN npx prisma db push

# Étape 7 : Exposer un port (ex : 3000)
EXPOSE 3000

# Étape 8 : Commande de démarrage (à adapter si tu as un fichier server.js ou app.js)
CMD ["npm", "start"]
