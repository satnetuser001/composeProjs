This is my first docker-compose project.
It consists of several images. The images do not interact with each other, they are simply an illustration of a multi-container application.
This contains a few additional settings for the backend image:
	tty and stdin_open for attach to container;
	depends_on for the order of containers start

To build an application:
	docker compose up -d

To attache to backend container:
	docker container attach first-compose-backend-1

To stop the application:
	docker compose down