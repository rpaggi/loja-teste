# loja-teste

## Para criar o container rodar:
docker run -d --name=lemp \
  -v /path/to/www/:/var/www/ \
  -v /path/to/mysql:/var/lib/mysql \
  -p port_of_nginx:80 \
  stenote/docker-lemp:latest
