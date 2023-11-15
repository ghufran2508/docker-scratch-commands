# docker-scratch-commands
---
```
FROM node:18

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

ENV PORT=5000

EXPOSE 5000

CMD [ "node", "server.js" ]
```
copy past this in express app Dockerfile

Then Make a build by running this command

```
docker build -t demoapp:0.0.1 .
```
where -t is for tag and . represent the working directory

Run the image by running this command

```
docker run -p 5000:8080 <image-id>
```
5000:8080 represents
local:container

port forwarding every request on port container:8080 to local:5000

where <image-id> is your container id.

you can check every container by running this command

```
docker ps
```
