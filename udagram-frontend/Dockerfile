# ## 
# FROM beevelop/ionic:latest AS ionic
# ## Créer le répertoire de l'application
# WORKDIR /usr/src/app
# # Installer les dépendances de l'application
# # Un joker est utilisé pour s'assurer que package.json ET package-lock.json sont copiés.
# COPY package*.json ./
# # Lancez npm ci
# RUN npm ci
# # Regroupement des sources de l'application
# COPY . .
# RUN ionic build
# ## Exécuter
# FROM nginx:alpine
# # COPY www /usr/share/nginx/html
# COPY --from=ionic /usr/src/app/www /usr/share/nginx/html
# # EXPOSE 80

FROM node:16.13.1 as ionic

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install -g npm@latest

RUN npm i -g @ionic/cli

RUN npm i --force

COPY . .

RUN ionic build

FROM nginx:alpine

#COPY www /usr/share/nginx/html
COPY --from=ionic /usr/src/app/www /usr/share/nginx/html
