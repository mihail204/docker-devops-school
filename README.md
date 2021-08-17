1. Adding local registry and running it on 500 port (port 5000 already in use on my server): </br>
docker run -d -p 500:5000 --restart=always --name registry registry:2

2. Cloning this repository and build images: </br>
git clone "https://github.com/mihail204/docker-devops-school.git" </br>
cd docker-devops-school </br>
cd Nginx_1 </br>
docker build -t localhost:500/web_1:1.0 -t localhost:500/web_1:latest . </br>
cd ../Nginx_2 </br>
docker build -t localhost:500/web_2:1.0 -t localhost:500/web_2:latest .


3. Push images to local registry: </br>
docker push localhost:500/web_1:1.0 </br>
docker push localhost:500/web_2:1.0

4. Run images using docker-compose: </br>
   cd ../ </br>
   docker-compose up

5. Checking: </br>
   Go to http://localhost:5555 for web_1 service and go to http://localhost:7777 for web_2 service
