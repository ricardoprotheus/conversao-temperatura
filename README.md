# conversao-temperatura

Hand-On

https://github.com/KubeDev/conversao-temperatura

Access the www.dockerhub.com, find Node, select image node oficial

Dockerfile - Allows create a new image with my expecifications, is the best
mkdir handons
cd handons
git clone https://github.com/KubeDev/conversao-temperatura.git
code .

Create file dockerfile

FROM node:17.4.0
WORKDIR /app
COPY package*.json ./ 
RUN npm install
COPY . .
EXPOSE 8080
CMD ["node", "server.js"]

PS: Or the best, for disable the cache of apt-get update

###

cd handons\conversao-temperatura\src
docker image build -t conversao-temperatura . - 
docker image ls
docker container run -d -p 8080:8080 conversao-temperatura
docker container ls

localhost:8080

docker container rm -f conversao-temperatura
