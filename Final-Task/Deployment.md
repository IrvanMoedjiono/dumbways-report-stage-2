## Deploy aplikasi housy

- Buat file bernama Dockerfile pada repositori housy frontend dan backend

Frontend
```
FROM node:dubnium-alpine3.11
WORKDIR /usr/src/app
COPY . .
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]
```

backend
```
FROM node:dubnium-alpine3.11
WORKDIR /usr/src/app
COPY . .
ENV DATABASE_URL postgres://root:root@10.224.143.55/housy
ENV NODE_ENV production

RUN npm install
RUN npm install serve
RUN npm install pg --save
RUN npm install -g sequelize-cli
RUN npm build
RUN sequelize-cli db:migrate --env production

EXPOSE 5000
CMD ["node", "index.js"]
```

- Buat file bernama docker-compose.yml pada repositori housy frontend dan backend untuk menjalankan 2 container pada setiap images

frontend
```
version: '3'
services:
  frontend1:
    build: .
    image: fro:1.0
    container_name: fro1
    stdin_open: true
    ports:
      - 3001:3000

  frontend2:
    image: fro:1.0
    container_name: fro2
    stdin_open: true
    ports:
      - 3002:3000
```

backend
```
version: '3'
services:
  backend1:
    build: .
    image: bac:1.0
    container_name: bac1
    stdin_open: true
    ports:
      - 5001:5000

  backend2:
    image: bac:1.0        
    container_name: bac2
    stdin_open: true
    ports:
      - 5002:5000
```

- Kemudian jalankan perintah `docker-compose build` pada setiap direktori frontend dan backend
- Cek Images apakah sudah terbuat dengan perintah `docker images`

<p align="center"><img src="../Final-Task/assets/Deployment/1.png"></p>

- Jalankan perintah `docker-compose up -d` untuk deploy aplikasi 

<p align="center"><img src="../Final-Task/assets/Deployment/2.png"></p>

- Buka web browser dan akses aplikasi-nya

<p align="center"><img src="../Final-Task/assets/Deployment/3.png"></p>

<p align="center"><img src="../Final-Task/assets/Deployment/4.png"></p>

<p align="center"><img src="../Final-Task/assets/Deployment/5.png"></p>
