Docker ile ubuntu image ini çekiyoruz ve bu ubuntu image üzerinde bir nodejs projesi oluşturup ubuntu image de çalıştırıyoruz. Bunu nasıl yapabiliriz? İki farklı yöntemde (manuel ve Dockerfile) ubuntu image üzerinde nodejs uygulamasını çalıştıralım.
1. Yöntem Adımları:
docker pull ubuntu
docker run -it ubuntu
apt-get update
apt-get install curl -y
curl -sL https://deb.nodesource.com/setup_10.x | bash
apt-get install nodejs -y
cd opt
mkdir node-app
cd node-app
nano index.js
echo 'console.log("nodejsapp from ubuntu...");' > index.js
node index.js

2.Yöntem Adımları:
index.js doyasını oluştur.
Dockerfile dosyasını oluştur.
```
FROM ubuntu:18.04
RUN apt-get update
RUN apt-get install curl -y
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install nodejs -y
WORKDIR /opt/node-app/
COPY . /opt/node-app/
ENV channel=hpoyraz
# COPY . .
# CMD ["node", "/opt/node-app/index.js"]
CMD ["node", "index.js"]
```
CLI : docker build . -t simple-node-app
CLI: docker run simple-node-app