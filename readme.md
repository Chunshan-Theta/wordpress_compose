#wordpress

##VW Setup

```commandline
sudo apt update
sudo apt install -y docker docker-compose
```

```commandline
sudo docker-compose -f docker-compose.yml.http pull
sudo docker-compose -f docker-compose.yml.http up -d
```

### SSL
```commandline
sudo docker-compose -f docker-compose.yml.http down
vim docker-compose_certbot.yml # 將 `ubestream.cf` 改成自己的網域
sudo docker-compose -f docker-compose_certbot.yml up
```

```commandline
sudo docker-compose -f docker-compose_certbot.yml down
vim nginx-conf-https/nginx.conf # 將 `ubestream.cf` 改成自己的網域
sudo docker-compose -f docker-compose.yml.https up
```