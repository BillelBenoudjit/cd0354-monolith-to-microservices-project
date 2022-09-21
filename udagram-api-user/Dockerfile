FROM node:12.22.9
# Créer le répertoire de l'application
WORKDIR /usr/src/app
# Installer les dépendances de l'application
# Un joker est utilisé pour s'assurer que le paquet.json ET le paquet-lock.json sont copiés lorsqu'ils sont disponibles (npm@5+)
COPY package*.json ./
# Lancez npm ci
# CMD ["npm", "i", "ts-node"]
# CMD ["npm", "ci"]
RUN npm i
# Regroupement des sources de l'application
COPY . ./
EXPOSE 8080
# CMD ["npm", "run", "build"]
CMD [ "npm", "run", "prod" ]