# Usa una imagen oficial de Node.js como base
FROM node:18-alpine

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Copia el package.json y el package-lock.json
COPY package*.json ./

# Instala las dependencias
RUN npm install

# Copia el resto del código fuente
COPY . .

# Exponer el puerto en el contenedor
EXPOSE 4000

# Define el comando que se ejecutará al iniciar el contenedor
CMD ["npm", "start"]
