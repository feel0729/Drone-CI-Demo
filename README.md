# Drone-CI-Demo
## 練習架設 Drone CI

參考 *用五分鐘安裝好 Drone 搭配 GitHub 自動化測試環境*

https://youtu.be/-U2EXs0tmN0

參考 *三分鐘學會Drone ，CI/CD輕鬆上手! Jesse 2020/04/14 11:00:00*

https://www.tpisoftware.com/tpu/articleDetails/1884

---

## 前置工作:

1. 安裝Docker，並學會使用docker-compose
2. 安裝ngrok
3. 撰寫檔案
   > docker-compose.yml

   > .env

## Drone CI 架設步驟:

1. 根據註解修改.env檔案,一併進行ngrok啟動及Github OAuth的設定
2. 執行指令
   > docker-compose -f "docker-compose.yml" up -d
3. 根據ngrok拿到的網址連入自己的Drone-CI網站
4. 在Github創個Repository並撰寫部署流水線定義檔
   > .drone.yml
5. 在本機Drone-CI網站將剛創的Repository啟動
6. 在Github上剛創的Repository修改幾個檔案，並commit & push
7. 到本機Drone-CI網站觀察部署流水線運行狀態

## 失敗了?請檢查:

1. docker-compose.yml中對外的port與ngrok起的port有沒有一致?
2. 啟動drone之前，Github OAuth需先設定完成。
3. 部屬流水線的設定檔有沒有設定好Trigger?

---

## 為什麼選擇 Drone ?
   
* Docker Hub上的image都能拿來當作部署流水線的一環
   > maven:3-jdk-8

   > appleboy/drone-ssh

   > drillster/drone-volume-cache
   
* 這也意味著可以自己打包一個image，應付各式各樣的部署需求

---

## **專案開發期光是探索使用者需求就夠你忙的了，枯燥乏味的步驟就交給無人機吧！**

---

在本機架設要靠NGROK轉址，機器有時windows更新後自動重開機，NGROK要重新設定

試著架設到AWS上的Elastic Beanstalk

平台選擇DOCKER

Elastic Beanstalk直接提供一組網址，把那組網址設定到.env DRONE_SERVER_HOST的欄位

Github上的App setting 也改為這組網址

*** 這邊要注意的是Elastic Beanstalk預設提供HTTP的服務，沒有HTTPS，要自己設定

接著把這兩個檔案打包成.zip檔，上傳後就可以使用了

   > docker-compose.yml

   > .env

2022-07-20 更新

---
