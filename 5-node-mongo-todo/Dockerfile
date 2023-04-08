FROM node:19-alpine3.16
WORKDIR /opt/node-todo-app
COPY . .
ENV PORT=4000
EXPOSE 4000
RUN npm install
CMD [ "node", "app.js" ]