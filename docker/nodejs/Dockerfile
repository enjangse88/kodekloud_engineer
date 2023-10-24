FROM node:latest

RUN mkdir /node_app
WORKDIR /node_app
COPY package.json .
COPY server.js .
RUN npm install
EXPOSE 8084
CMD ["node","server.js"]