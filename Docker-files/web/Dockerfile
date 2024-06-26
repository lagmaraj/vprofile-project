FROM nginx:latest

LABEL Project="Vprofile"
LABEL Author="Raju"

# Remove the default Nginx configuration
RUN rm -rf /etc/nginx/conf.d/default.conf

# Copy the custom Nginx configuration file
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf

