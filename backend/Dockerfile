FROM node:20-slim
WORKDIR /app
COPY package*.json ./
RUN npm ci && npm install -g nodemon
COPY . .
ENV PORT=4000
ENV MONGO_URL="mongodb://mongo:27017/grocery"
ENV JWT_SECRET="jwtsecrect"
ENV ADMIN_EMAIL="admin@example.com"
ENV ADMIN_PASSWORD="admin123"
EXPOSE 4000
CMD [ "npm", "run", "server" ]