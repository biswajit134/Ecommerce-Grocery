FROM node:21 AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
ENV VITE_CURRENCY="$"
ENV VITE_BASEURL="http://135.235.161.107:4000"
RUN npm run build

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
COPY --from=build /app/dist ./
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]