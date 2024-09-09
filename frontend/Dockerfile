# Etapa 1: Construir el proyecto
FROM node:18-alpine AS build

# Establece el directorio de trabajo en el contenedor
WORKDIR /app

# Copia el package.json y package-lock.json (si existe) al contenedor
COPY package*.json ./

# Instala las dependencias
RUN npm install

# Copia el resto del código fuente al contenedor
COPY . .

# Construye la aplicación para producción
RUN npm run build

# Etapa 2: Servir el proyecto con Nginx
FROM nginx:alpine

# Copia los archivos construidos desde la etapa anterior
COPY --from=build /app/build /usr/share/nginx/html

# Exponer el puerto en el contenedor
EXPOSE 80

# Inicia Nginx
CMD ["nginx", "-g", "daemon off;"]

