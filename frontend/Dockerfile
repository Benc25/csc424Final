# Stage 1: Build the React application
FROM node:22-alpine AS build
WORKDIR /app
# Copy package files and install dependencies
COPY package*.json ./
RUN npm install
# Copy the rest of the source code and build
COPY . .
RUN npm run build

# Stage 2: Serve the application with Nginx
FROM nginx:alpine
# Vite outputs the build to the 'dist' folder by default
COPY --from=build /app/dist /usr/share/nginx/html
# Expose port 80 for the container
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]