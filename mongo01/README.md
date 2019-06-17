# ความรู้เบื้องต้นเกี่ยว NoSQL

> NoSQL Introduction

## จุดประสงค์รายสัปดาห์


1. สามารถอธิบายระบบฐานข้อมูลแบบ NoSQL ได้

2. สามารถติดตั้งระบบฐานข้อมูล mongodb ได้

3. สามารถอธิบายและยกตัวอย่าง database collection และ document ได้

4. สามารถสร้าง database collection และ document ตามที่โจทย์ต้องการได้ (mongo-express / mongo-compass)

**อ้างอิง**

* สำหรับจุดประสงค์ที่ 1 

  - https://www.slideshare.net/badraccount/nosql-databases-70526495

  - https://www.slideshare.net/quipo/nosql-databases-why-what-and-when

* สำหรับจุดประสงค์ที่ 2-4 

  - https://www.slideshare.net/wlaforest/an-introduction-to-big-data-nosql-and-mongodb

  - mongo-compass - https://docs.mongodb.com/compass/current/install/

  - mongo-express - https://github.com/mongo-express/mongo-express

## การติดตั้ง ![MongoDB](/assets/images/mongodb-logo.png)

### ติดตั้งด้วยวิธีปกติของระบบปฏิบัติการ

#### Ubuntu

* เพิ่ม server เพื่อติดตั้ง

```sh
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
```

* สั่ง update และติดตั้ง

```sh
sudo apt update
sudo apt install -y mongodb-org
```

#### Windows

* Download: https://www.mongodb.com/download-center/community?jmp=docs

* คู่มือการติดตั้ง: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/

#### MacOS

* Download: https://www.mongodb.com/download-center/community?jmp=docs

* คู่มือการติดตั้ง: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/

### ติดตั้งด้วย `docker-compose`

* เขียนไฟล์ `docker-compose.yml`

```yml
version: '3.1'

services:

  mongo:
    image: 'mongo'
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: admin
      MONGO_INITDB_ROOT_PASSWORD: cs@ubu

  mongo-express:
    image: mongo-express
    restart: always
    ports:
      - 8081:8081
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: admin
      ME_CONFIG_MONGODB_ADMINPASSWORD: cs@ubu
```

* เปิด `cmd.exe` ที่ตำแหน่งเดียวกับไฟล์ `docker-compose.yml` ใช้คำสั่ง

```sh
docker-compose up
```

* คำสั่งนี้จะเปิด mongo server ที่ port 27017 และ mongo-express ที่ 

http://localhost:8081

