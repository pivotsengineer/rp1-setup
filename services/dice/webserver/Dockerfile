# Use the Nginx image from Docker Hub
FROM nginx:alpine

# Remove the default Nginx index.html
RUN rm /usr/share/nginx/html/*

# Copy your index.html into the Nginx server
COPY ./index.html /usr/share/nginx/html/index.html

# Expose port 80
EXPOSE 80

# Start Nginx when the container launches
CMD ["nginx", "-g", "daemon off;"]
