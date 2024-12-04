This is a single container application based on ubuntu:latest image.
This contains a few additional settings for the ubuntu image:
	tty and stdin_open for attach to container;
	depends_on for the order of containers start

To run the application, run the command:
	docker compose up -d

To attach to the ubuntu container, run the command:
	docker container attach single-container-app-ubuntu-1

To stop the application:
	docker compose down