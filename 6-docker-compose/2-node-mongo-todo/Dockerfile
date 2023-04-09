FROM node:19-alpine3.16
WORKDIR /opt/node-todo-app
COPY app/ .
RUN npm install
CMD [ "node", "app.js" ]