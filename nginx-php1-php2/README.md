Host with nginx web server and several php-fpm web applications working in docker containers.

Request from the client, it is suggested to use Postman, is processed by nginx web server and
transmitted according to the FastCGI protocol in PHP-FPM through docker network as shown in
the diagram.

<pre>
   +-----------------+
   |     client      |
   |     Postman     |
   +--------+--------+
            |             +----------------------+        +----------------------+
            | request --- |  localhost:8090      | --or-- |  localhost:8090      |
            |             |  host->app1.example  |        |  host->app2.example  |
            V             +----------------------+        +----------------------+
      +-----------+
      | nginx     |
      | container |
      +-----+-----+
            |
            | routing to web applications
            | in docker network "nginx-php1-php2"
            V
     --+--------------------+--------------------+------->
       |                    |                    |
       V                    V                    V
+--------------+     +--------------+     +--------------+
| web app php1 |     | web app php2 |     | web app phpN |
| container    |     | container    |     | container    |
+--------------+     +--------------+     +--------------+
</pre>

To run execute in current directory:
docker compose up -d


To rebuild exist images and run execute in current directory:
docker compose up -d --build


To attach to a container shell:
docker exec -it container-name bash


To see the result:
-in Postman create GET request to 127.0.0.1:8090 and in Headers
add Key:host with Value:php1.example or with Value:php2.example
-or open Postman saves in "postman" directory


To remove all execute in current directory:
docker compose down


Other:
-in the nginx directory has the default nginx setting in the "default.conf" file