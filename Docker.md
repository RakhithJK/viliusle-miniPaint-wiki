There are few versions.

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

```
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

```
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

