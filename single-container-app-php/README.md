This is a single container application based on php:latest image.
This uses a PHP script with an infinite loop to be able to attach to the container.

To run the application, run the command:
	docker compose up -d

To attach to the php container with bash, run the command:
	docker exec -it single-container-app-php-1 bash

To view the output of the php script in the container run:
	docker logs -f single-container-app-php-1
or
	docker container attach single-container-app-php-1
or run the application without -d flag:
	docker compose up

To stop the application:
	docker compose down