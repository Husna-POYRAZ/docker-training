FROM node:19-alpine3.16
WORKDIR /opt/node-server
COPY app/ .
RUN npm install
EXPOSE 3000
CMD ["node", "app.js"]