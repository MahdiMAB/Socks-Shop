FROM node:10-alpine

# Définir les variables d'environnement
ENV NODE_ENV=development
ENV PORT=8079

# Créer l'utilisateur et le groupe
RUN addgroup -S mygroup && adduser -S -G mygroup -u 1010 myuser -s /bin/sh myuser

# Créer le répertoire et donner les bonnes permissions
WORKDIR /usr/src/app
RUN chown -R myuser:mygroup /usr/src/app

# Copier package.json et yarn.lock en premier pour optimiser le cache
COPY package.json yarn.lock ./

# Installer les dépendances en tant que root pour éviter les problèmes de permission
RUN yarn install

# Copier le reste du code
COPY . .

# Passer à l'utilisateur non root
USER myuser

# Exposer le port et lancer l'application
EXPOSE 8079
CMD ["node", "server.js"]
