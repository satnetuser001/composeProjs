# base image
FROM php:latest

# create a working directory inside the container for the php script
WORKDIR /app

# copy the php script
COPY src/index.php ./

# run php script when container starts
ENTRYPOINT ["php", "index.php"]