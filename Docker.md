There are few versions (sorted by date).

## [Ange-Cesari](https://github.com/Ange-Cesari) [2023-04-10]

Simply follow these steps to generate the image yourself: 

pre-requesite : docker & git 

Step 1 : Go into a folder on your local machine and git clone the miniPaint project: 
```bash
git clone https://github.com/viliusle/miniPaint.git
```

Step 2 : Create a dockerfile at the root folder of the project and paste the following code : 

```dockerfile
#Written by Ange Cesari
# Use official Node.js based on Alpine
FROM node:16-alpine

# Create dir for application
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm i

# Copy the rest of the application code
COPY . .

# Expose the port the application will run on
EXPOSE 8080

# Run the application
CMD ["npm", "run", "server"]
```

Step 3 : Build the image : 
```bash
docker build -t minipaint .
```

Step 4 : Once i'ts built, run the container and bind the ports :
```bash
docker run -d -p 8080:8080 --name minipaint-container minipaint
```

Step 5 : Once the container is started, you should be able to reach `http://localhost:8080`

## [CreativeCactus](https://github.com/CreativeCactus) [2023-03-23]

Create file `Dockerfile` at the root folder of the project and paste the following code:

```dockerfile
FROM node:alpine3.17
EXPOSE 8080/tcp
WORKDIR /app
COPY ./package* ./
RUN npm ci
COPY ./ ./
RUN npm run build
ENTRYPOINT [ "npm", "run" ]
CMD [ "server-prod" ]
# For development inside docker: -v ./:/app minipaint server
```

To run, use:

`docker build -t minipaint . && docker run -itp 8080:8080 minipaint`

## [ghost](https://github.com/ghost) [2023-03-01]

Create file `Dockerfile` at the root folder of the project and paste the following code:

```dockerfile
# https://github.com/bluenevus/docker-minipaint
FROM centos:latest
EXPOSE 8080/tcp
RUN yum update -y
RUN yum install epel-release -y
RUN yum install git -y
RUN yum install curl -y
RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN yum install nodejs -y
RUN npm install -g npm -y
RUN mkdir /var/www
WORKDIR /var/www
RUN git clone https://github.com/viliusle/miniPaint.git
WORKDIR /var/www/miniPaint
RUN npm update -y
RUN npm init -y
CMD bash -c "npm run server"
```






## [PootisPenserHere](https://github.com/PootisPenserHere) [2020-11-29]

Basic Dockerfile with multi-stage to build the static version and deploy it with nginx.

Create a dockerfile at the root folder of the project and paste the following code : 

```dockerfile
# Stage 1 - the build process
FROM node:12 as build-deps

WORKDIR /usr/src/app

COPY package.json /usr/src/app
COPY package-lock.json /usr/src/app
RUN npm install

COPY . /usr/src/app
RUN npm run build

# Stage 2 - the production environment
FROM nginx:1-alpine

COPY --from=build-deps /usr/src/app/dist /usr/share/nginx/html/dist
COPY --from=build-deps /usr/src/app/index.html /usr/share/nginx/html
COPY --from=build-deps /usr/src/app/images /usr/share/nginx/html/images

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```
