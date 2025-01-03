docker stop mt5_1 && docker rm mt5_1
docker-compose down
docker image prune -a
docker volume prune
docker build -t mt5 .
docker run -d --name mt5_1 -p 3000:3000 -v /root/py:/py mt5
docker exec -it mt5_1 bash


docker commit mt5_1 mt5:v1.0

#convert file sh 
cd ..
cd MetaTrader
apt-get update && apt-get install -y dos2unix
dos2unix start.sh


docker images

https://www.mql5.com/en/forum/457940
https://github.com/gmag11/MetaTrader5-Docker-Image/tree/main
https://github.com/lucas-campagna/mt5linux