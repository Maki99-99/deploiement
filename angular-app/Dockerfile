# ---------- Stage 1: build the Angular app with Node.js ----------
FROM node:16-alpine AS build
WORKDIR /app

# Copy only the dependency list first (better Docker cache)
COPY package*.json ./
RUN npm install --force

# Copy the rest of the source code, then build
COPY . .
RUN npm run build --force

# ---------- Stage 2: serve the static files with Nginx ----------
FROM nginx:1.17.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/dist/angular-app /usr/share/nginx/html
EXPOSE 80
