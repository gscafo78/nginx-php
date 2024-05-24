<img src="https://www.svgrepo.com/download/373924/nginx.svg" alt="NGINX" width="200"/>

<img src="https://clipart-library.com/images_k/php-logo-transparent/php-logo-transparent-11.png" alt="PHP" width="400"/>



# Docker Nginx and php-fpm

Nginx and php 8.3.3, the faster way to deploy nginx and php for your websites.

# Requirement

Docker must be configured to run Linux  / Windows Docker containers.
Here the full documentation helping you [install docker ](https://docs.docker.com/engine/install/)

# Create Docker Image

```shell
# Change directory to project folder
cd nginx-php/build

# Build Docker image
docker build -t 4ss078/nginx-php:latest .
```

# Run Docker Container

```shell
# Run Docker container in interactive mode
# Make sure you replace `<your_path>` with your target folder, this is where files will be created.
# To generate the Certification Authority just create the container

docker run -it --rm -v your_path:/var/www/html/ -p 80:80 4ss078/nginx-php:latest
```
