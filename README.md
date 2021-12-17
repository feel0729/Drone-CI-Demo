# Drone-CI-Demo
練習架設 Drone CI

參考 "用五分鐘安裝好 Drone 搭配 GitHub 自動化測試環境"
https://youtu.be/-U2EXs0tmN0

參考 "三分鐘學會Drone ，CI/CD輕鬆上手! Jesse 2020/04/14 11:00:00"
https://www.tpisoftware.com/tpu/articleDetails/1884

前置工作
1.安裝Docker，並學會使用docker-compose
2.安裝ngrok
3.pull Drone-CI-Demo

Drone CI 架設步驟
1.根據註解修改.env檔案,一併進行Github OAuth的設定
2.執行指令docker-compose -f "docker-compose.yml" up -d
3.根據ngrok拿到的網址連入自己的Drone-CI網站
4.在Github創個Repository並撰寫部署流水線定義檔.drone.yml
5.在自己架的Drone-CI網站將剛創的Repository Activate
6.在Github上剛創的Repository修改幾個檔案,並commit & push
7.到自己架的Drone-CI網站觀察部署流水線運行狀態

*因為是參考他人教學網誌，所以就只記錄自己對Drone-CI架設步驟的理解
