# Step 1: Build the app
FROM node:18-alpine AS build
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Step 2: Serve using Nginx
FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html   # For Vue/React (Vite)
# COPY --from=build /app/build /usr/share/nginx/html # For CRA React
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]